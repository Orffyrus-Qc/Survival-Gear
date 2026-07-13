# 03 — Démarrage automatique et ATS (systèmes en cas de panne)

**Objectif :** quand le réseau tombe, le système **démarre le moteur**, **vérifie la qualité d’alimentation**, **bascule la maison**, puis **retourne au réseau** en sécurité.

Termes :

- **Démarrage auto / automatic start** — le contrôleur lance le moteur sans vous  
- **Auto-allumage** — expression informelle pour démarrage électrique + lancement auto (essence/GN/LP = allumage par étincelle ; diesel = compression + préchauffage)  
- **ATS** — Automatic Transfer Switch (commutateur de transfert automatique)  
- **AMF** — Automatic Mains Failure (fonction contrôleur)

---

## 1. Blocs du système

```
[Réseau utilité] ----\
                      \
                       [ ATS / transfert ] ---- [ Charges maison ]
                      /
[Génératrice secours] /
       ↑
[Batterie de démarrage + chargeur]
       ↑
[Contrôleur : sense utilité, crank, chauffe, exercice]
       ↑
[Carburant : GN / propane / diesel]
```

| Bloc | Rôle |
|------|------|
| Capteurs tension utilité | Détecter panne / creux |
| Contrôleur génératrice | Crank, huile/temp/Hz/V, alarmes |
| Batterie de démarrage | Ampères de lancement ; float-chargée quand le réseau est là |
| Moteur + alternateur | Produire 120/240 V 60 Hz |
| ATS | Déconnecter utilité, connecter génératrice (break-before-make) |
| Planificateur d’exercice | Course hebdo pour joints et batterie |

---

## 2. Séquence de panne (typique)

1. **L’utilité tombe** (ou V/Hz hors fenêtre).  
2. Le contrôleur attend un court **délai** (évite les démarrages sur micro-coupures).  
3. **Crank** du moteur (plusieurs tentatives avec pauses).  
4. Le moteur tourne ; tension/fréquence se stabilisent.  
5. Délai de **chauffe** optionnel.  
6. **L’ATS bascule** les charges sur la génératrice.  
7. Course sous charge ; surveillance défauts (huile basse, survitesse, surcharge).  
8. **L’utilité revient** et reste stable un **délai de retour**.  
9. L’ATS rebascule sur l’utilité.  
10. Course de **refroidissement**, puis arrêt.  
11. La batterie de démarrage se recharge via le chargeur alimenté par le réseau.

Si le démarrage échoue : alarme / notification appli. Retour aux procédures manuelles.

---

## 3. Types d’ATS (intermédiaire)

### ATS panneau entier

Bascule tout le service (dans la limite de la génératrice).

### ATS entrée de service

Placement spécial par rapport au compteur/principal — **design électricien**.

### Sous-panneau de charges critiques / géré

Seuls les disjoncteurs essentiels sur le bus génératrice.  
Génératrice plus petite, coût moindre, intelligent pour le chauffage canadien.

### Modules de gestion de charge

Certains systèmes délestent cuisinière, sécheuse, borne VE pour qu’une gen moyenne couvre plus de la maison.

### Transfert manuel (pas automatique)

Vous démarrez la gen et basculez l’interrupteur — moins cher, fiable si vous êtes là.

---

## 4. Interverrouillage vs ATS (ne pas confondre)

| Dispositif | Démarrage auto ? | Transfert auto ? | Usage typique |
|------------|------------------|------------------|---------------|
| **Interverrouillage** de disjoncteurs | Non | Non | Portable + entrée, plus conforme qu’une réinjection illégale |
| Commutateur de transfert **manuel** | Non | Non | Manette après démarrage gen |
| **ATS** | Souvent avec forfait secours | Oui | Pannes sans surveillance |

**Jamais** de cordon mâle-mâle « suicide » dans une prise de sécheuse.

---

## 5. Ce que signifie « système d’auto-allumage » en pratique

Pour le secours résidentiel :

1. **Batterie 12 V de démarrage** saine toute l’année.  
2. **Chargeur / tender** a besoin du réseau quand il est présent.  
3. **Allumage par étincelle** (essence/LP/GN) ou **préchauffage/crank diesel** géré par ECU.  
4. **Électrovanne carburant** s’ouvre seulement en marche.  
5. Capteurs : pression d’huile, température liquide, survitesse, etc.

**Batterie de démarrage faible = raison n°1 d’« échec auto pendant le verglas ».**  
Tester/remplacer selon calendrier ; cosses propres ; batterie à bon CCA pour le Canada.

---

## 6. Génératrices portables et « automatisation »

| Montage | Réalité |
|---------|---------|
| Démarrage électrique + télécommande | Vous branchez encore cordons / basculez interverrouillage |
| Contrôleurs aftermarket | DIY avancé ; facile de mal faire — préférer kits listés |
| Onduleur + EcoFlow qui se recharge | Batterie couvre les courts blips ; gen pour longues pannes **manuellement** |
| Transfert avec contacts de démarrage gen | Certains commutateurs envoient un signal de start aux gensets compatibles |

Pour un **vrai secours maison sans surveillance**, acheter un **forfait secours + ATS listé** installé au code.

---

## 7. Installation et code (orientation Canada)

- **Électrique :** Code canadien de l’électricité (CEC) + amendements provinciaux ; permis + électricien licencié.  
- **Québec :** travail souvent sous catégories **RBQ** ; permis municipaux.  
- **Gaz :** train GN/propane par technicien gaz licencié ; distances aux fenêtres/limites.  
- **Placement :** échappement loin des portes, fenêtres, prises d’air frais ; détecteurs CO dans la maison.  
- **Liaison neutre :** le schéma de neutre de la génératrice doit matcher le matériel de transfert — mauvaise liaison = dangereux.

Ce projet **ne remplace pas** un design licencié.

---

## 8. Exercice hebdomadaire et entretien

La plupart des secours **s’auto-démarrent chaque semaine** ~5–20 minutes.

Liste :

- [ ] Courses d’exercice complètes (historique appli)  
- [ ] Pas de codes de défaut  
- [ ] Niveau d’huile / changements (heures)  
- [ ] Filtre à air, bougies (moteurs à étincelle)  
- [ ] Carburant : niveau LP ; fuites GN par pro au besoin  
- [ ] Tension / âge batterie de démarrage (souvent 2–5 ans)  
- [ ] Neige/glace hors admission, échappement, enceinte  
- [ ] Test sous vraie charge une fois par saison (frigo + soufflerie)  

---

## 9. Modes de panne en panne de réseau

| Symptôme | Cause probable |
|----------|----------------|
| Pas de crank | Batterie morte, fusible, huile froide, démarreur |
| Crank sans départ | Valve carburant, LP vide, étincelle/préchauffage, noyé |
| Tourne mais pas de maison | ATS ne bascule pas, disjoncteur off, surcharge |
| Bascule puis meurt | Surcharge, huile basse, famine carburant |
| Démarre trop souvent sur blips | Réglages de délai de sense |
| Alarme CO dans la maison | Fuite échappement / mauvais placement — arrêter, évacuer, corriger |

---

## 10. Exercices pratiques (sans imprudence)

1. Esquisser votre panneau : principal, disjoncteur gen, entrée.  
2. Étiqueter les charges critiques pour un futur sous-panneau.  
3. Jour portable : démarrage complet, tension au multimètre, charge connue.  
4. Remplacer ou tester la batterie de démarrage avant l’hiver.  
5. Lire une fois la séquence ATS du manuel de votre marque.

Suite → [`../04_Canadian_Brands_Best_Fit/README.md`](../04_Canadian_Brands_Best_Fit/README.md)
