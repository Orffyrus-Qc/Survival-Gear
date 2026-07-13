# 01 — EcoFlow : pratique de base → niveau intermédiaire

EcoFlow sert ici de **plateforme pédagogique** : station d’alimentation portable (PPS) qui combine batterie, BMS, entrées de charge et onduleur. Une fois EcoFlow compris, les autres « génératrices solaires » (Jackery, Bluetti, Anker, Goal Zero, etc.) se cartographient facilement.

> **Objectif intermédiaire :** expliquer chaque port, choisir un panneau compatible Voc/Isc, étendre la capacité correctement, diagnostiquer les pannes courantes sans deviner.

---

## 1. Ce qu’est EcoFlow (architecture)

| Bloc dans l’unité | Rôle |
|-------------------|------|
| Pack batterie LiFePO4 (ou NMC sur certains anciens modèles) | Stocke l’énergie (Wh sur la boîte) |
| BMS (système de gestion batterie) | Protège les cellules : surcharge, sous-décharge, surintensité, température |
| Chargeur CA / double charge | Charge depuis le mur (parfois auto + CA ensemble) |
| Entrée solaire (MPPT) | Convertit la puissance panneau en charge sûre |
| Onduleur | CC batterie → CA domestique (sinus pur sur les modèles modernes) |
| Sorties CC | USB-A/C, prise allume-cigare 12 V, parfois Anderson / CC extra |
| Écran / appli | État de charge (SoC), watts entrée/sortie, défauts |

**Idée clé :** vous **ne choisissez pas** un contrôleur séparé pour l’entrée solaire EcoFlow — le MPPT est **à l’intérieur**. Vous ne faites que respecter les **limites de tension/courant** de l’entrée solaire.

---

## 2. Spécifications qui comptent

Avant tout câble solaire, notez pour **votre** modèle :

| Spec | Signification | Pourquoi |
|------|---------------|----------|
| Capacité (Wh) | Énergie utilisable (approx.) | Estimation d’autonomie |
| Type de batterie | LFP vs NMC | Cycles, règles par temps froid |
| Entrée solaire max (W) | Plafond de récolte | Un plus grand champ ne dépasse pas ce plafond |
| Plage de tension solaire (V) | Fenêtre de travail | Trop bas = pas de charge ; trop haut = risque de dommage |
| Tension en circuit ouvert max Voc | Limite absolue panneau | **Chiffre anti-dommage le plus important** |
| Courant de court-circuit max Isc | Limite de courant | Surintensité = déclenchement ou dommage |
| Sortie CA (W continu / crête) | Ce que vous pouvez faire tourner | Les moteurs demandent une marge de démarrage |
| Limites de température de charge | Interdiction charge à froid | Le LFP refuse souvent de charger près de 0 °C |

*Les chiffres changent selon le modèle et l’année. Habitude : Voc d’abord, watts ensuite.*

---

## 3. Ports — identification pratique

### Entrées (énergie entrante)

1. **Entrée CA** — câble chargeur mural.  
2. **Solaire / auto XT60 (ou similaire)** — beaucoup d’EcoFlow utilisent **XT60**. Polarité critique.  
3. **Solaire extra / double PV** sur grands modèles — 2ᵉ canal MPPT ; Voc par canal.  
4. **Batterie d’extension** — uniquement extensions EcoFlow de la bonne ligne.

### Sorties (énergie sortante)

1. **Prises CA** — onduleur allumé. Consommation à vide : éteindre si inutile.  
2. **USB-A / USB-C PD** — efficace pour téléphones, tablettes, certains portables.  
3. **Prise 12 V** — frigos 12 V, radios, compresseurs (surveiller les ampères continus).  
4. **DC5521 / Anderson** (selon modèle).

**Habitude survie :** préférer CC et USB à l’onduleur CA quand possible — moins de pertes.

---

## 4. Première mise sous tension (zéro dommage)

1. Inspecter bosses, liquide, ports écrasés.  
2. Charger au **mur** jusqu’à ~100 % une fois (calibration SoC).  
3. Noter ventilateur, odeur (aucune = bon), appairage appli.  
4. Décharger avec une petite charge connue (USB) et vérifier Wh / %.  
5. Ensuite seulement le solaire.

---

## 5. Branchement solaire — ordre EcoFlow

### Chemin de câble

```
Panneau MC4  →  MC4-vers-XT60 (ou câble solaire EcoFlow)  →  port solaire XT60 EcoFlow
```

### Règles

1. **Couvrir le panneau** ou le détourner du soleil pendant le branchement.  
2. Confirmer polarité de l’adaptateur au multimètre.  
3. Série vs parallèle :
   - **Série** : les Voc s’additionnent — respecter le Voc max.  
   - **Parallèle** : les Isc s’additionnent — respecter le courant max.  
4. Rester **dans** la fenêtre de tension EcoFlow.  
5. Ombre, angle et vitre sale tuent plus de watts que la marque.

### Liste solaire

- [ ] Voc du champ (froid prévu) ≤ Voc max de l’unité  
- [ ] Tension de travail dans la plage MPPT  
- [ ] Section de câble suffisante  
- [ ] Pas de pins MC4 forcés dans de mauvais adaptateurs  
- [ ] Détente de traction (vent, bâche)  

---

## 6. Ce qu’EcoFlow fait (et ne fait pas)

| Fait | Ne fait pas |
|------|-------------|
| Prévenir beaucoup de surcharges/sous-décharges via BMS | Réparer une polarité inversée forcée |
| Récolte MPPT de panneaux compatibles | Accepter n’importe quelle string haute tension de toit |
| CA sinus pur (modèles modernes) pour l’électronique | Remplacer un commutateur de transfert / installation maison entière (sauf kit prévu) |
| Mises à jour firmware | Faire marcher des extensions d’autres marques |

---

## 7. Diagnostics niveau intermédiaire

| Symptôme | Cause probable | Vérifier |
|----------|----------------|----------|
| 0 W solaire, beau temps | Voc trop bas, polarité, panneau couvert, mauvais port | Multimètre en bout de câble |
| Charge puis arrêt tôt | Surchauffe, limite BMS, SoC plein | Chaleur ambiante, grilles |
| Onduleur coupe sous charge | Surcharge ou crête | W continus vs crête |
| Code d’erreur appli | Protection | Manuel ; reset après refroidissement |
| Autonomie bien sous les Wh | Rendement onduleur + veille | Mesurer watts réels ; utiliser le CC |

---

## 8. Exercices pratiques

1. **Carte des ports :** dessiner de mémoire.  
2. **Audit de charges :** 5 charges de survie en Wh.  
3. **Calcul Voc :** deux panneaux Voc 20 V en série → 40 V. Sous le max ?  
4. **Taxe de veille :** drain nuit onduleur on vs off.  
5. **Règle froid :** chimie + température minimale de charge.

---

## 9. Écosystème EcoFlow (intermédiaire)

- **Station portable (PPS) :** autonome.  
- **Batterie extra :** capacité seulement, même ligne.  
- **Kits maison intelligente (haut de gamme) :** circuits résidentiels — pas du matériel de camp débutant.  
- **Panneaux officiels :** connecteurs pratiques ; tiers OK si Voc/Isc match.  
- **Firmware :** corrections de courbes de charge.

---

## 10. Pont vers la suite

EcoFlow cache contrôleur et bus batterie. Les sections suivantes **ouvrent la boîte conceptuellement**.

Suite → [`../02_Identify_Components/README.md`](../02_Identify_Components/README.md)
