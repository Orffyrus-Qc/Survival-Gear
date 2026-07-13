# Énergie solaire — collecte et stockage

**Niveau :** pratique de base → intermédiaire  
**Marque de départ (apprentissage intégré) :** EcoFlow  
**Objectif :** comprendre comment le solaire est collecté, régulé, stocké et utilisé — y compris marques mixtes et constructions en récupération.

**English :** [`../../Solar_Energy_Gathering_And_Storage/README.md`](../../Solar_Energy_Gathering_And_Storage/README.md)

## Ce que vous saurez faire

1. Alimenter et charger une station type EcoFlow depuis le mur et le solaire sans abîmer ports ni câbles.
2. Identifier panneau, contrôleur de charge, batterie, onduleur, fusible et multimètre.
3. Câbler une chaîne hors réseau dans le **bon ordre** pour que contrôleurs et batteries survivent.
4. Décider quand mélanger panneaux / contrôleurs / batteries / marques est sûr — et quand non.
5. Comparer les grandes marques de génératrices solaires portables et DIY par architecture, pas par marketing.
6. Assembler un **système solaire 12 V basique en récup** avec limites de sécurité claires.

## Ordre d’étude

| # | Dossier | Sujet |
|---|---------|--------|
| 01 | [`01_EcoFlow_Hands_On/`](./01_EcoFlow_Hands_On/) | EcoFlow du déballage à l’entrée solaire |
| 02 | [`02_Identify_Components/`](./02_Identify_Components/) | Reconnaître chaque pièce et lire les étiquettes |
| 03 | [`03_Safe_Assembly/`](./03_Safe_Assembly/) | Ordre de branchement, polarité, bonnes habitudes |
| 04 | [`04_Mixed_Brand_Systems/`](./04_Mixed_Brand_Systems/) | Panneau + contrôleur + batterie + marques différents |
| 05 | [`05_US_Brands_How_They_Work/`](./05_US_Brands_How_They_Work/) | Marques courantes en Amérique du Nord |
| 06 | [`06_Scrap_Electronics_Build/`](./06_Scrap_Electronics_Build/) | Système basique à partir de récupération |
| — | [`reference/`](./reference/) | Fiches, connecteurs, glossaire |

## Chemin d’énergie (à mémoriser)

```
SOLEIL
   ↓
PANNEAU(X) SOLAIRE(S)  →  (CC, tension variable)
   ↓
CONTRÔLEUR DE CHARGE  (PWM ou MPPT)  →  régule la charge batterie
   ↓
BATTERIE  (stockage)
   ↓
ONDULEUR (optionnel)  →  CA pour prises domestiques
   et/ou
CHARGES CC  (lumières, 12 V, convertisseurs USB)
```

**Unités intégrées (EcoFlow, Jackery, Bluetti, Anker, etc.)** : contrôleur + batterie + onduleur + BMS dans un boîtier.  
**Systèmes DIY / récup** : boîtiers séparés — plus flexible, plus d’erreurs possibles.

## Démarrage rapide (aujourd’hui)

1. Lire **01_EcoFlow_Hands_On** même avec une autre marque — la logique des ports est similaire.
2. Pratiquer **02** avec un vieux transformateur, une batterie auto ou un panneau d’occasion.
3. **Ne pas** sauter aux packs lithium de récup avant d’avoir fini 03 et 04.

## Outils pour le niveau intermédiaire

| Outil | Pourquoi |
|-------|----------|
| Multimètre numérique (V CC, continuité) | Confirmer tension et polarité avant de brancher |
| Connecteurs / adaptateurs type MC4 | Connexions panneau sûres |
| Porte-fusibles en ligne + fusibles adaptés | Protéger câbles et batteries |
| Pince à dénuder, sertisseuse, gaine thermo | Fiabilité mécanique |
| Pinces croco (fusibles si possible) | Tests temporaires seulement |
| EPI : lunettes, gants isolants si énergie élevée | Yeux et mains |

## Contexte survie

1. **Fiabilité de charge** avant les watts de pointe  
2. **Chimie de batterie connue** avant la « haute capacité mystère »  
3. **Petits systèmes redondants** plutôt qu’une seule station fragile  
4. **Éclairage et radios 12 V CC** avant de gros onduleurs CA  

Pour pannes hivernales multi-jours, charges de démarrage élevées et maisons sans surveillance, voir  
[`../Generators_Gas_Diesel_Auto_Start/`](../Generators_Gas_Diesel_Auto_Start/).

---

Suivant : [`01_EcoFlow_Hands_On/README.md`](./01_EcoFlow_Hands_On/README.md)
