# 02 — Portable vs secours résidentiel (standby)

Deux outils différents. Les confondre gaspille de l’argent et crée des installations dangereuses.

---

## 1. Côte à côte

| | **Portable** | **Secours résidentiel** |
|--|--------------|-------------------------|
| Emplacement | À roulettes dehors au besoin | Dalle permanente près de la maison |
| Démarrage | Lanceur / bouton électrique / télécommande | Démarrage auto en panne (avec ATS) |
| Carburant | Essence, diesel, dual-fuel LP | Souvent **GN ou propane** (diesel industriel parfois) |
| Raccordement | Cordons ou **entrée manuelle** + interverrouillage/transfert | **ATS** câblé au panneau |
| Coût | Centaines–quelques milliers CAD | Plusieurs milliers + installation |
| Idéal | Chalet, charges partielles | Résidence principale auto-secours |

---

## 2. Classes de portables

### Onduleur (inverter) — silencieux, CA plus propre

Honda EU, Yamaha EF, Westinghouse iGen, Generac iQ, etc.  
Meilleur pour : électronique, charge de stations solaires, petit frigo.

### Open-frame conventionnel

Plus bruyant, watts moins chers.  
OK pour scies, thermoplongeurs, pompes (si crête OK).  
Vérifier **watts de démarrage** vs continus.

### Dual-fuel / tri-fuel à roues

Kit « tempête » populaire en grande surface.  
Propane pour le stockage + essence pour le max de puissance.

---

## 3. Classes de secours

| Taille typique | Rôle |
|----------------|------|
| 7–12 kW | Circuits critiques : frigo, lumières, soufflerie, puisard, modem |
| 14–22 kW | Plus large partiel ou petite maison entière (sans gros chauffage électrique) |
| 24 kW+ / refroidi liquide | Grandes maisons, puits, multi-AC, léger commercial |

**Chauffage électrique / thermopompes / bornes VE** changent tout le calcul — souvent **pas** toute la maison sur un petit secours.

---

## 4. Dimensionner sans deviner

1. Sommer les **watts continus** des charges critiques simultanées.  
2. Ajouter la marge du **plus gros démarrage moteur**.  
3. Choisir la note continue de la génératrice **au-dessus** ; ne jamais planifier sur la crête comme continu.  
4. Viser ~50–80 % de charge pour durée de vie (surtout diesel).

| Charge | W continus (ordre) | Démarrage |
|--------|--------------------|-----------|
| Frigo | 100–800 | 3–5× brièvement |
| Soufflerie fournaise | 100–800 | crête |
| Pompe de puisard | 800–1500 | forte |
| Pompe de puits | souvent haute | très haute |
| Micro-ondes | 1000–1500 | — |
| Plinthe 1500 W | 1500 | — |

---

## 5. Comment le courant entre dans la maison

### A. Cordons seulement (portable)

Cordons extérieurs, bon calibre (ex. 12 AWG pour longs 15 A).  
Jamais sous les tapis à long terme.

### B. Boîte d’entrée + transfert manuel / interverrouillage

```
Génératrice → entrée d’alimentation (extérieur) → commutateur de transfert OU interverrouillage de disjoncteurs → disjoncteurs choisis
```

- **Kit d’interverrouillage :** glissière physique pour que le principal utilité et le disjoncteur génératrice ne soient pas ON ensemble  
- **Commutateur de transfert manuel :** sous-panneau de charges critiques  

### C. ATS + secours (démarrage auto)

```
Utilité ──┐
          ATS ──→ Panneau maison / sous-panneau critique
Génératrice ─┘
```

Voir section 03 pour la séquence complète.

---

## 6. Identifier les composants

| Pièce | Apparence |
|-------|-----------|
| Prise génératrice L14-30 / 14-50 | Twist-lock ou style VR sur la gen |
| Boîte d’entrée | Entrée mâle étanche sur mur extérieur |
| Commutateur de transfert | Boîtier mural positions utilité/gen |
| ATS | Souvent près du panneau principal ; contacteur + contrôleur |
| Contrôleur génératrice | LCD/boutons sur l’unité de secours |
| Batterie (secours) | Batterie 12 V de démarrage dans l’unité — l’entretenir |

---

## 7. « Démarrage auto » portable ?

Certaines portables ont **démarrage électrique + télécommande**. Ce n’est **pas** un système ATS maison :

| Fonction | Démarrage remote portable | Vrai secours auto-start |
|----------|---------------------------|-------------------------|
| Détecte panne réseau | Rarement | Oui |
| Bascule les charges maison | Non | Oui via ATS |
| Auto-test hebdomadaire | Rare | Courant |
| Multi-jours sans vous | Pauvre | Conçu pour |

---

## 8. Réalités Canada / chalet

- **Chalets :** dual-fuel portable + entrée manuelle souvent meilleur ROI  
- **Maison principale, verglas, appareils médicaux :** secours GN/LP + ATS  
- **Appartements / condos :** balcons interdisent souvent les gén (CO + règlements) — stations batterie  
- **Règlements de bruit** existent hors urgence  

Suite → [`../03_Auto_Start_ATS_Outage/README.md`](../03_Auto_Start_ATS_Outage/README.md)
