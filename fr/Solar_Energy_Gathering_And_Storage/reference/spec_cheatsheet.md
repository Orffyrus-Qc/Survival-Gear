# Aide-mémoire des spécifications

## Faits rapides tension

| Système | Nominal | Repos plein (approx.) | Absorb charge typique (approx. — vérifier !) |
|---------|---------|----------------------|-----------------------------------------------|
| Plomb 12 V | 12 V | ~12,7 V | ~14,4–14,7 V |
| LiFePO4 12 V (4s) | 12,8 V | ~13,3–13,6 V | ~14,2–14,6 V (fabricant/BMS) |
| Banque 24 V | 24 V | ~25,4 V (plomb) | classe ~28,8 V |
| Banque 48 V | 48 V | ~50,8 V (plomb) | classe ~57,6 V |

## « Panneau 12 V » vs volts réels

Un « panneau 12 V » n’est **pas** à 12 V au soleil. Typique :

| | Approx. |
|--|---------|
| Vmp | 17–19 V |
| Voc | 21–23 V |

Cette marge est normale pour charger une batterie 12 V via un contrôleur.

## Calcul d’autonomie (brut)

```
Heures ≈ (Wh batterie × fraction utilisable) / W de charge
Wh batterie ≈ Tension × Ah
```

Fractions utilisables typiques :

- Plomb survie : planifier souvent **50 %** DoD  
- LFP : souvent **80–90 %** si BMS sain  

Charges onduleur : diviser par ~0,85–0,9 (pertes).

## Dimensionnement contrôleur (esquisse)

```
A de charge ≈ W panneau / V batterie
Choisir contrôleur ≥ × 1,25 de marge
```

## Courant fil (très approximatif — trajets courts)

| AWG | Continu ballpark (court, cuivre, air libre) |
|-----|-----------------------------------------------|
| 16 | ~10 A |
| 14 | ~15 A |
| 12 | ~20 A |
| 10 | ~30 A |
| 8 | ~40–50 A |
| 4 | ~70–85 A |
| 2 | ~95–115 A |

## Avertissement Voc froid

Le Voc du panneau **monte** par temps froid. Laisser une marge sous le Voc max du contrôleur.

## Modèle mental EcoFlow / PPS

```
Panneau tiers OK ⇔ Voc et courant dans le manuel de la station
Extension de capacité = seulement la ligne officielle de la marque
```

## Ordre de branchement (à tatouer)

```
DIY : Batterie → Contrôleur → Panneaux → Charges
PPS solaire : Vérifier polarité → Couvrir panneau → Brancher → Découvrir
```
