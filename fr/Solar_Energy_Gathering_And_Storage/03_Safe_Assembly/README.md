# 03 — Assemblage sûr (sans endommager le matériel)

La plupart des dommages DIY ne viennent pas d’« électronique mystère ». Ils viennent d’un **mauvais ordre**, d’une **mauvaise polarité**, d’une **surtension** ou de **fusibles absents**.

---

## 1. Règles d’or (mémoriser)

1. **Batterie d’abord, panneaux en dernier** pour les contrôleurs autonomes.  
2. **Polarité à chaque fois** — multimètre avant sertissage permanent.  
3. **Fusible au + batterie** avant les longs parcours de câble.  
4. **Voc sous le max** du contrôleur/station (estimer le Voc froid pour les séries).  
5. **Même tension système** — batterie 12 V avec réglages 12 V.  
6. **Une chimie, un profil de charge.**  
7. **Couvrir les panneaux** pendant les premiers branchements.  
8. **Pas de torsade nue** comme joint permanent — sertir, cosse, connecteur propre.  
9. **Détente de traction** sur chaque connecteur.  
10. **En cas de doute, stop** — re-mesurer ; ne pas « essayer pour voir » sur le lithium.

---

## 2. Ordre de branchement correct (DIY autonome)

### Mise sous tension

```
1. Fixer la batterie (zone ventilée si plomb ouvert)
2. Installer le porte-fusible sur le + BATTERIE (fusible hors ou ouvert)
3. Brancher contrôleur BAT+ / BAT− sur la batterie (bonne polarité)
4. Insérer le fusible — le contrôleur démarre, affiche V batterie
5. Régler le type de batterie (SLA / AGM / LFP) si menu
6. Brancher les panneaux sur PV+ / PV− (couverts d’abord)
7. Découvrir les panneaux — confirmer ampères/watts de charge
8. Ensuite seulement onduleur ou charges CC (lignes fusibles propres)
```

### Coupure / service

```
1. Couvrir panneaux ou ouvrir disjoncteur PV
2. Débrancher PV du contrôleur
3. Couper charges / onduleur
4. Ouvrir fusible/disjoncteur batterie
5. Débrancher contrôleur de la batterie si besoin
```

### Pourquoi batterie avant panneau ?

Beaucoup de PWM/MPPT utilisent la tension batterie comme référence et alimentation logique. Les panneaux seuls peuvent **détruire** le contrôleur.

---

## 3. Ordre station portable (classe EcoFlow)

```
1. Unité selon le manuel
2. Vérifier polarité du câble solaire au multimètre
3. Couvrir le panneau
4. Brancher le câble dans le port solaire
5. Découvrir / viser le soleil
6. Confirmer les watts d’entrée à l’écran
```

---

## 4. Polarité — motifs de dommage

| Erreur | Résultat fréquent |
|--------|-------------------|
| Batterie inversée sur contrôleur | Contrôleur grillé |
| Panneau inversé | Pas de charge, stress possible |
| Onduleur inversé | Étincelle, dommage, incendie |
| Adaptateurs XT60 forcés | Polarité inversée dans la station |

**Habitude :** rouge = +, noir = − — mais **toujours vérifier** les câbles de récup ; les couleurs mentent.

---

## 5. Assemblage mécanique sans dommage

### Panneaux

- Soutenir le cadre ; ne pas marcher sur le verre.  
- Ne pas trop serrer les fixations (microfissures).  
- Flexibles : pas de pliage net.  
- MC4 : clic jusqu’au verrouillage ; outil de déverrouillage.

### Contrôleurs

- Dissipateur aéré ; ne pas enterrer dans de la mousse.  
- Vis de bornes : fermes, non arrachées — cosses anneau adaptées.

### Batteries

- SLA : position selon design ; pas d’étincelles près des évents.  
- LiFePO4 : protéger la carte BMS des chocs.  
- Ne pas marteler les cosses sur plots mous.

### Fils

- Dénuder juste assez.  
- Sertir correctement ; test de traction.  
- Gaine thermo.  
- Câbles onduleur courts et épais.

---

## 6. Assemblage électrique

### Série vs parallèle panneaux

- **Série :** tensions s’ajoutent, courant ~identique → surveiller Voc.  
- **Parallèle :** courants s’ajoutent, tension ~identique → câbles plus gros, fusibles par string.  
- Wattages mixtes en série : le plus faible Imp limite le string.

### Dimensionnement courant contrôleur

Exemple : 200 W vers batterie 12 V ≈ 200 / 12 ≈ 16,7 A → contrôleur **≥ 20 A** avec marge.

---

## 7. Dimensionnement protection (pratique)

1. Courant continu max du parcours.  
2. Fusible ≤ ampacité du câble, ≥ charge continue (ou tableau fabricant).  
3. Fusible près de la source d’énergie (+ batterie côté charge).  

Câble trop petit + fusible trop gros = **incendie avec fusible « qui marche »**.

---

## 8. Protocole de premier essous tension

1. Inspection visuelle.  
2. Continuité : fusible bon ; pas de court BAT+/BAT− charges coupées.  
3. Tension batterie seule — plage saine.  
4. Contrôleur sur batterie seule — réglages OK.  
5. Voc panneau **débranché**.  
6. Brancher PV, confirmer courant de charge sensé.  
7. Petite charge CC.  
8. Onduleur en dernier avec une lampe connue.

---

## 9. Scénarios de dommage courants

| Scénario | Prévention |
|----------|------------|
| Contrôleur sur PV avant batterie | Batterie d’abord |
| String Voc 60 V dans MPPT max 50 V | Calcul Voc + facteur froid |
| LFP chargé en profil plomb pour toujours | Régler Li / V correctes |
| Câbles 16 AWG sur onduleur 1000 W | Section correcte |
| Outil métallique pontant les plots | Couvrir les plots |

---

## 10. Liste d’assemblage

- [ ] Chimie identifiée  
- [ ] Tension système choisie (12/24/48)  
- [ ] Contrôleur supporte chimie + tension  
- [ ] Voc champ ≤ max contrôleur/station  
- [ ] Ampères contrôleur ≥ attendu avec marge  
- [ ] Fusible au + batterie  
- [ ] Section de fil OK  
- [ ] Polarité vérifiée  
- [ ] Ordre batterie → contrôleur → panneau  
- [ ] Réglages sauvés  
- [ ] Protection chaleur et météo  
- [ ] Tensions notées  

Suite → [`../04_Mixed_Brand_Systems/README.md`](../04_Mixed_Brand_Systems/README.md)
