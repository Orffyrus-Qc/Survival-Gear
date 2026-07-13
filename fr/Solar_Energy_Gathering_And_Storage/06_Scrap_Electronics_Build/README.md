# 06 — Construire un système basique en récupération électronique

**Objectif :** un système qui marche **12 V solaire → contrôleur → batterie → lumière/USB** avec des pièces de récup ou d’occasion, sans partir le feu.

Éducation **survie**, pas installation maison conforme au code.

---

## 1. Périmètre du « système récup basique »

| Bloc | Cible débutant |
|------|----------------|
| Tension | **12 V seulement** |
| Panneau | 20–100 W récup / occasion |
| Contrôleur | PWM bon marché 10–30 A |
| Batterie | **Plomb étanche (SLA/AGM) 7–100 Ah** de préférence pour l’apprentissage |
| Sortie | LED 12 V, téléphone via buck USB, onduleur petit plus tard |
| Pas en v1 | Strings haute tension, packs Li-ion ordi sans BMS, injection réseau |

### Pourquoi SLA d’abord en récup ?

- Plus tolérant aux réglages imparfaits que des cellules lithium nues  
- Courant dans ASI (UPS), alarmes, scooters, jouets  
- Modes de panne visibles (gonflement → retirer)  
- Toujours polarité + ventilation / sécurité  

**LiFePO4 drop-in** excellent s’il est **connu bon avec BMS** — composant connu, pas piles mystères.

---

## 2. Non-négociables sécurité (récup)

1. Protection des yeux sur les batteries.  
2. Fusible sur le + batterie — toujours.  
3. Pas de bijoux aux mains sur les plots.  
4. Pas de charge de pochettes lithium de récup sans BMS et savoir-faire.  
5. Isolation de fil de récup douteuse jusqu’à inspection.  
6. Première mise sous tension dehors ou surface non inflammable.  
7. Sectionneur (interrupteur ou retrait de fusible) à portée.  
8. Batterie chaude, gonflée ou qui sent → **isoler dehors, fin de vie**.

---

## 3. Où récupérer (réaliste Canada / US)

| Source | Ce qu’on obtient | Attention |
|--------|------------------|-----------|
| ASI (UPS) mort | SLA 12 V, parfois fils | Pack sulfuré possible |
| Alarmes / éclairages de secours | Petits SLA | Faible Ah |
| Scooter / auto pour enfants | Batteries 12 V, chargeurs | Chargeurs « bêtes » |
| VR / remorques | Panneaux, câbles, contrôleurs | Dégâts météo |
| Lampes de jardin solaires | Minuscules panneaux | Jouet éducatif |
| Friperie / Marketplace | Panneaux, kits, onduleurs | Watts affichés douteux |
| Casse auto (si compétent) | Fils, fusibles, cosses | Batterie démarreur ≠ cycle profond |
| Clôture électrique / ferme | Petits panneaux | Boîtes de jonction pourries |

### Laisser / avancé seulement

- Pochettes Li-ion gonflées  
- 18650 nues sans protection  
- Alims serveur haute tension sans isolation connue  

---

## 4. Liste de pièces — minimum viable

| Qté | Pièce | Spec |
|-----|-------|------|
| 1 | Panneau solaire | « 12 V nominal » ≈ Voc 17–22 V typique |
| 1 | Contrôleur PWM | ≥ 10 A ; type batterie sélectionnable si possible |
| 1 | SLA/AGM 12 V | 7–20 Ah pour apprendre ; plus si charges l’exigent |
| 1 | Fusible + support | ex. 10–30 A selon fil/contrôleur |
| Fil | Rouge/noir | Courts trajets 12–14 AWG petits systèmes |
| 1 | LED 12 V | ~1–5 A max premier test |
| 1 | Multimètre | Obligatoire |
| Option | Buck USB 12 V→5 V | Charge téléphone |
| Option | Petit onduleur sinus | Après que le CC marche |
| Option | Connecteurs MC4 | Remplacer fils coupés |

---

## 5. Tester avant d’assembler

### Panneau

1. Nettoyer le verre.  
2. Au soleil, mesurer **Voc** (souvent dizaines de V pour classe 12 V).  
3. Voc ~0 en plein soleil → panneau mort ou diode/jonction ouverte.  
4. Polarité au multimètre.

### Batterie

1. Tension au repos (~12,0–12,8 V peut être utilisable ; ~10 V souvent morte).  
2. Fissures / gonflement.  
3. Plots propres.  
4. Si chargeur connu : charge lente et voir si elle tient.

### Contrôleur

1. Pas d’odeur de brûlé.  
2. Bornes étiquetées.  
3. Alimentation **batterie seule** d’abord — ~12 V affiché.

---

## 6. Schéma de câblage (basique)

```
                    [PANNEAU SOLAIRE]
                     +        -
                  PV+      PV-   (contrôleur)
              +------+--------+------+
              |   CONTRÔLEUR DE CHARGE|
              +------+--------+------+
                  BAT+     BAT-
                     |        |
                    [FUSIBLE] |
                     |        |
                     +--[BATTERIE 12V]-+
                     |                 |
                     +----(charges)----+
                           |
                    [LED / buck USB]
```

---

## 7. Étapes d’assemblage

### 1 — Disposition mécanique

Planche, bac plastique (non hermétique si plomb qui ventile), batterie calée.

### 2 — Batterie → fusible → contrôleur

1. Porte-fusible à quelques cm du BAT+.  
2. BAT− contrôleur → − batterie.  
3. BAT+ → fusible → + batterie.  
4. Insérer le bon fusible.  
5. Affichage ~12 V.  
6. Mode **étanche / AGM** (pas Li sauf batterie LFP).

### 3 — Panneau → contrôleur

1. Couvrir panneau.  
2. PV− puis PV+ (polarité).  
3. Découvrir ; indication de charge.  
4. Tension batterie monte lentement au soleil, charge coupée.

### 4 — Charge CC

LED via petit fusible si possible. Succès #1 : la lumière s’allume.

### 5 — USB

Buck 12 V → vérifier 5 V → puis téléphone.

### 6 — Documenter

Voc, habitudes de V batterie, tailles de fusibles sur une carte collée au bac.

---

## 8. Recettes de récup

### A — Résurrection ASI (table)

- SLA 7–9 Ah d’ASI mort (recycler l’électronique responsablement).  
- Panneau 20–40 W.  
- PWM 10 A.  
- Spots LED.  

### B — Boîte camp batterie scooter

- 12 V 20–35 Ah mobilité (si saine).  
- Panneau 50–100 W.  
- PWM/MPPT 20 A.  
- Fusible 20–30 A.  
- Onduleur 150–300 W optionnel pour portable brièvement.

### C — Deux panneaux en parallèle

- Voc similaires, branche MC4, un contrôleur.  
- Ampères contrôleur ≥ somme Imp + marge.

### D — Pas recommandé en premier

- Parallèle de batteries d’outils au hasard.  
- Séries de packs ordi sans BMS.  
- Panneau direct sur batterie avec une diode seulement (sauf démo jetable acceptée).

---

## 9. Critères de succès « première lumière »

- [ ] Contrôleur affiche V batterie panneau couvert  
- [ ] Au soleil, ampères de charge ou LED « charging »  
- [ ] V batterie monte en 30–60 min (charge coupée)  
- [ ] LED tourne sur batterie après le coucher  
- [ ] Aucun composant trop chaud au toucher  
- [ ] Fusibles ne sautent qu’en vrai défaut  

---

## 10. Dépannage

| Problème | Vérifications |
|----------|---------------|
| Pas de charge | Voc, polarité, contrôleur grillé, nuit, ombre |
| Contrôleur noir | Fusible, batterie morte, polarité inversée |
| Batterie ne monte jamais | Grosse charge, cellule morte, panneau trop petit, mauvaise connexion |
| Odeur de fondue | Surintensité, fil trop petit — couper |
| Téléphone refuse | Limite du buck ; comparer à un USB mural |

---

## 11. Notes éthiques et légales

- Récupérer seulement ce qui est abandonné / à vous / acheté.  
- Recycler le plomb correctement — toxique.  
- Ne pas réinjecter les prises de maison depuis un onduleur (îlotage dangereux).  

---

Retour module → [`../README.md`](../README.md)  
Références → [`../reference/`](../reference/)
