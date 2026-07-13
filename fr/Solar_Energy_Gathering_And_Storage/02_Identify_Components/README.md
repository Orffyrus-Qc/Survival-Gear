# 02 — Identifier les composants

Si vous pouvez **le nommer, le mesurer et lire ses limites**, vous assemblez ou récupérez sans deviner.

---

## 1. Les cinq blocs (tout système)

| # | Composant | Rôle en une ligne | Apparence typique |
|---|-----------|-------------------|-------------------|
| 1 | Panneau solaire (module PV) | Lumière → électricité CC | Rectangle verre, cellules, boîte de jonction, fils MC4 |
| 2 | Contrôleur de charge | Charge sûre de la batterie depuis le panneau | Petit boîtier alu : PV+, PV−, BAT+, BAT−, parfois LOAD |
| 3 | Batterie | Stocke l’énergie | Bloc lourd (SLA) ou LiFePO4 avec fils BMS |
| 4 | Onduleur | CC → CA | Boîte avec câbles batterie + prises murales |
| 5 | Protection et câblage | Stopper les incendies, permettre la coupure | Fusibles, disjoncteurs, sectionneurs, câbles, cosses |

**« Génératrice solaire » intégrée** = 2 + 3 + 4 + BMS dans un boîtier (EcoFlow etc.).

---

## 2. Panneau solaire

### Visuel

- Avant : grille de cellules sous verre ou polymère  
- Arrière : plaque signalétique, boîte de jonction, deux câbles  
- Connecteurs : souvent **MC4**

### Champs de la plaque

| Étiquette | Signification |
|-----------|---------------|
| Pmax / Watt | Puissance nominale (conditions standard) |
| Vmp | Tension à puissance max |
| Imp | Courant à puissance max |
| Voc | Tension circuit ouvert (la plus haute) |
| Isc | Courant de court-circuit (le plus haut) |

### Multimètre

1. **Voc :** soleil, entre + et −.  
2. **Polarité :** lecture positive = + correct.  
3. Ne pas court-circuiter Isc « pour le fun » sur gros panneaux.

### Indices de récup survie

Toits de VR, lampes de jardin (minuscules), enseignes, kits d’occasion, panneaux de clôture électrique agricole.

---

## 3. Contrôleur — PWM vs MPPT

| | PWM | MPPT |
|--|-----|------|
| Coût | Plus bas | Plus haut |
| Rendement | Moins bon si V panneau >> V batterie | Meilleur ; suit le point de puissance max |
| Appariement panneau | V panneau proche de la charge batterie | Fenêtre de tension plus large |
| Usage typique | Petits kits 12 V, récup | Panneaux mixtes, plus de puissance |

**Habitude fatale à désapprendre :** ne jamais alimenter le contrôleur par les seuls panneaux sans batterie (beaucoup de modèles exigent la batterie d’abord).

---

## 4. Batterie — identifier la chimie d’abord

| Type | Indices | V nominale (classe 12 V) | Attention charge |
|------|---------|--------------------------|------------------|
| Plomb ouvert (flooded) | Bouchons d’eau, lourd | ~12,0–12,7 repos | Ventiler ; gaz |
| AGM / Gel SLA | Étanché, « sans entretien » | ~12,0–12,8 | Profil AGM/gel |
| LiFePO4 (LFP) | Souvent BMS Bluetooth, plus léger | ~12,8 (4s) | Tension LFP ; BMS requis |
| NMC / piles ordi | 18650, packs d’outils | Variable | **Avancé seulement** |

### Tension au repos (plomb 12 V, approx.)

| V repos | État approximatif |
|---------|-------------------|
| ~12,7+ | Plein |
| ~12,2 | ~50 % |
| ~11,9 ou moins | Bas — arrêter la décharge |

---

## 5. Onduleur

| Étiquette | Signification |
|-----------|---------------|
| Watts continus | Ce qu’il peut tenir longtemps |
| Watts de crête | Démarrage moteur court |
| Tension d’entrée | 12 / 24 / 48 V = banque batterie |
| Forme d’onde | Sinus modifié (bon marché) vs sinus pur (mieux pour l’électronique) |

---

## 6. Protections

| Pièce | Rôle |
|-------|------|
| Fusible ANL / MEGA / MIDI | Protection CC fort courant |
| Fusible lame (ATO) | Branches plus faibles |
| Disjoncteur CC | Protection + sectionnement |
| Barre de bus | Jonction multi-câbles propre |

**Règle :** fusible **aussi près que possible du + batterie**, dimensionné pour le **câble**.

---

## 7. Connecteurs et fils

| Connecteur | Usage courant |
|------------|---------------|
| MC4 | Strings de panneaux |
| XT60 / XT90 | Stations portables, CC fort |
| Anderson SB / Powerpole | Treuils, DIY CC |
| Cosses anneau / fourche | Bornes batterie et onduleur |
| DC5521 | Accessoires sur certaines stations |
| SAE 2 broches | Mainteneurs solaires, kits |

Fil : plus épais = numéro AWG plus petit (8 AWG plus gros que 14 AWG).

---

## 8. Compétences multimètre

1. **Tension CC** — batterie et Voc panneau  
2. **Continuité** — câble, fusible non ouvert  
3. **Polarité** — avant chaque premier branchement  
4. (Optionnel) **Courant CC** — pince ampèremétrique de préférence  

---

## 9. Logigramme rapide

```
Verre + cellules + deux fils CC ? → PANNEAU
Bornes PV + BAT, ~12–48 V ? → CONTRÔLEUR
Lourd, deux gros plots, classe 12 V ? → BATTERIE (vérifier chimie)
Prises murales sur boîtier alimenté en CC ? → ONDULEUR
Sur le + batterie / câble ? → FUSIBLE / DISJONCTEUR
Tout-en-un LCD + CA + port solaire ? → STATION PORTABLE
```

Suite → [`../03_Safe_Assembly/README.md`](../03_Safe_Assembly/README.md)
