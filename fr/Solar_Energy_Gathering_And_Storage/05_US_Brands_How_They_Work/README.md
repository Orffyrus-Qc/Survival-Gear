# 05 — Marques courantes en Amérique du Nord et leur fonctionnement

Focus : marques réellement achetées pour **stations solaires portables**, **DIY 12/24/48 V** et **secours maison**. Le marché change chaque année ; les **architectures** restent stables.

*Vue d’ensemble (milieu des années 2020) — pas un classement publicitaire.*

---

## 1. Deux marchés, deux architectures

| Marché | Ce que vous achetez | Fonctionnement |
|--------|---------------------|----------------|
| **Station portable (PPS) / « génératrice solaire »** | Une boîte + panneau optionnel | Batterie + BMS + MPPT + onduleur intégrés |
| **DIY composants / hors réseau** | Panneau, SCC, batterie, onduleur séparés | Vous assemblez ; plus réparable et mixable |

Compétence survie : PPS pour la **vitesse et la sécurité** ; DIY pour la **réparation, la récup et l’échelle**.

---

## 2. Stations portables courantes

### EcoFlow

| | |
|--|--|
| **Position** | Riche en fonctions, charge CA rapide, écosystème appli |
| **Architecture** | LiFePO4 sur la plupart des lignes actuelles ; MPPT interne ; solaire type XT60 ; extensions officielles |
| **Fonctionnement** | Mur/solaire/auto → charge multi-entrées → pack géré BMS → sorties CC + onduleur sinus |
| **Lignes (concept)** | River (portable), Delta (moyen/grand), Pro/Ultra (secours maison) |

### Jackery

| | |
|--|--|
| **Position** | Très répandue grand public ; UX simple |
| **Architecture** | Station intégrée + panneaux SolarSaga ; ports solaires souvent propriétaires |
| **Idéal pour** | Débutants qui veulent peu de décisions |

### Bluetti

| | |
|--|--|
| **Position** | Bon rapport Wh/$, expansion modulaire fréquente |
| **Architecture** | Packs LFP courants ; entrée CA + PV ; stacking de capacité |

### Anker (lignes SOLIX / power house)

| | |
|--|--|
| **Position** | Forte présence magasin ; confiance accessoires téléphone |
| **Architecture** | PPS LFP moderne ; appli ; mêmes limites solaires que les pairs |

### Goal Zero

| | |
|--|--|
| **Position** | Héritage outdoor / aventure (Yeti, panneaux) |
| **Architecture** | PPS + écosystème modulaire historique |

### Autres vues en rayon / en ligne

Pecron, Oupes, Fanttik, etc. (segment valeur) — même architecture ; vérifier garantie et support.

**À retenir :** presque chaque PPS est la même machine dans un plastique différent. Comparer **Wh, fenêtre Voc solaire, W onduleur continus, chimie, expansion, vitesse de charge**.

---

## 3. Marques DIY / composants courantes

### Panneaux

Renogy, Rich Solar, HQST, Newpowa, BougeRV, kits grande surface, panneaux résidentiels d’occasion (souvent Voc élevé).

### Contrôleurs

| Marque | Notes |
|--------|-------|
| **Victron Energy** | Premium, excellents docs, Bluetooth, sérieux DIY |
| **EPEver / EPsolar** | MPPT milieu de gamme populaire |
| **Renogy** | PWM/MPPT assortis aux kits |
| **Morningstar** | Longue réputation |
| **PWM générique** | OK pour petit 12 V récup si limites respectées |

### Batteries

Battle Born, Renogy, Eco-Worthy, LiTime / Ampere Time, Chins, etc. (LFP 12 V « drop-in ») ; racks 48 V (EG4…) pour maison DIY ; AGM/plomb encore courants.

### Onduleurs / onduleurs-chargeurs

Victron MultiPlus, Growatt, EG4, MPP Solar, AIMS, Giandel, Samlex, etc.

### Chaîne DIY (indépendante de la marque)

```
Panneaux (n’importe lesquels)
  → MPPT/PWM (réglé sur la chimie batterie)
    → Batterie + BMS (LFP) ou plomb
      → Onduleur ou charges CC
```

---

## 4. Comment chaque architecture « pense »

### A. PPS intégrée

```
[Panneau] --CC--> [MPPT interne] --charge--> [Cellules + BMS] --CC--> [USB/12V]
                                              |
                                              +--> [Onduleur] --CA--> prises
```

### B. Hors réseau classique 12/24 V

```
[Panneau] --> [SCC] --> [Banque batterie] --> [Onduleur]
                           |
                           +--> Tableau fusibles CC
```

### C. Hybride murale AIO

```
[Panneaux] --> [Onduleur hybride AIO] <--> [Batterie]
                    |
                    +--> Charges maison / revente (si légal)
```

### D. Hybride génératrice (réalité survie)

```
Solaire le jour → batterie
Génératrice essence/propane → chargeur CA quand le soleil manque
```

---

## 5. Priorité d’apprentissage pour ce projet

1. **EcoFlow ou PPS similaire** — habitudes I/O solaires sûres.  
2. **Kit 12 V type Renogy ou SCC type Victron** — vrais composants.  
3. **LiFePO4 12 V drop-in avec BMS** — standard de stockage DIY moderne.  
4. **Onduleur sinus pur adapté à la banque**.  
5. **SLA de récup + PWM** — urgence / apprentissage (section 06).

---

## 6. Crédo d’indépendance de marque

> Si la tension de l’étiquette matche et le profil de chimie est correct, le logo peut être n’importe quoi.  
> Si le logo matche mais le Voc est faux, le logo ne sauvera pas le contrôleur.

Suite → [`../06_Scrap_Electronics_Build/README.md`](../06_Scrap_Electronics_Build/README.md)
