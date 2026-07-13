# 04 — Systèmes multi-marques

**Les panneaux, contrôleurs, batteries et marques n’ont pas besoin du même logo.**  
Ils doivent correspondre en **limites électriques, chimie et communication (s’il y en a).**

Compétence clé en survie : on trouve rarement un kit parfaitement assorti sur le terrain ou en friperie.

---

## 1. Hiérarchie de compatibilité

```
1. TENSION SYSTÈME     (12 / 24 / 48 V)     — règle dure
2. CHIMIE              (plomb vs LFP vs autre) — règle dure pour la charge
3. LIMITES DE TENSION  (Voc, V de charge, coupures) — règle dure
4. LIMITES DE COURANT  (A contrôleur, fil, BMS) — règle dure
5. CONNECTEURS         (adaptateurs OK si polarité correcte) — souple
6. MARQUE / APP / BUS  (CAN, extensions propriétaires) — seulement si requis
```

**La marque est en dernier.** Tension et chimie d’abord.

---

## 2. Panneaux mixtes

### Même marque non requise

Tout panneau cristallin peut alimenter un contrôleur si :

- **Voc** du champ ≤ tension PV max du contrôleur  
- Courant du champ ≤ max du contrôleur (avec marge)  
- Câblage et fusibles sains  

### Série

- Courants similaires (Imp proches).  
- Le panneau faible / ombré limite le string.  
- Les tensions s’ajoutent → facile de dépasser le Voc max.

### Parallèle

- **Vmp proches** (idéalement à quelques volts).  
- Fusible par string en parallèle multiple : bonne pratique.

### Note station portable

EcoFlow / Bluetti / Jackery / Anker acceptent des panneaux tiers. Respecter **plage de tension et polarité du connecteur**, pas la marque du verre.

---

## 3. Contrôleurs mixtes

### Une règle simple

- **Un** cerveau de charge intelligent par banque batterie.  
- Deux chargeurs non coordonnés peuvent se disputer la tension.

### PWM marque A + batterie marque B

OK. Régler le **menu type batterie** sur la chimie, pas sur la marque du panneau.

### MPPT marque C + panneaux marque D

OK. Dimensionner pour Voc et watts.

---

## 4. Batteries mixtes (grande prudence)

| Mélange | Verdict |
|---------|---------|
| Neuve + très vieille, même chimie, parallèle | Mauvais |
| Ah différents en parallèle | Possible si même chimie/tension/âge similaire ; partage inégal |
| Ah différents en série | **Non** |
| Plomb parallèle avec LiFePO4 | **Non** sur le même string |
| Extensions portables d’une autre marque | **Ne se branchent pas** (bus propriétaire) |

### Motifs sûrs

1. Même chimie, même V nominale, capacité et âge proches, câbles de longueur égale.  
2. Batteries séparées, contrôleurs séparés, charges séparées = deux systèmes.  
3. LFP de marque connue avec tension documentée + MPPT supportant le profil LFP.

---

## 5. Matrice de décision — « Puis-je brancher ? »

### Panneau → Contrôleur / PPS

| Vérification | OK si |
|--------------|-------|
| Voc_champ | ≤ entrée PV max |
| Vmp / V de travail | Dans la plage MPPT (ou sensé pour PWM) |
| Isc / Imp | ≤ limite de courant |
| Connecteur | Adaptateur existe, polarité vérifiée |

### Contrôleur → Batterie

| Vérification | OK si |
|--------------|-------|
| V système | Contrôleur en 12/24/48 correct |
| Tension de charge | Correspond à la chimie (valeurs du fabricant batterie) |
| Courant de charge | ≤ A max batterie |
| Température | Dans les limites de charge |

---

## 6. Exemples réalistes

### A — Camp « frankenstein »

- Panneau 100 W type Renogy  
- PWM générique 20 A  
- LiFePO4 100 Ah avec BMS  
- Vieux onduleur sinus pur 300 W  

**OK si :** mode Li ou tensions correctes, Voc dans les limites, fusibles présents.

### B — EcoFlow + panneau friperie

- EcoFlow River/Delta  
- Panneau 200 W sans nom, MC4  
- Câble MC4→XT60  

**OK si :** Voc dans la plage, polarité correcte.

### C — Échec classique

- 3 panneaux 12 V en série → Voc ~66 V  
- Contrôleur max 50 V  
- Résultat : contrôleur mort  

**Correctif :** 2S ou parallèle, ou MPPT à Voc plus élevé.

---

## 7. Fiche terrain multi-marques

```
Panneau marque/modèle: ________  Voc: ____  Vmp: ____  Imp: ____  Pmax: ____
Config champ:  __S  __P   Voc champ: ____  Imp champ: ____

Contrôleur/PPS: ________  Voc max: ____  A max: ____  Modes batterie: ________

Batterie: ________  Chimie: ________  V: ____  Ah: ____  A charge max: ____

Onduleur: ________  W cont: ____  V entrée: ____

Fusibles: Contrôleur ____  Onduleur ____  String PV ____

Polarité vérifiée: [ ]   Batterie d’abord: [ ]   Notes: ________
```

Suite → [`../05_US_Brands_How_They_Work/README.md`](../05_US_Brands_How_They_Work/README.md)
