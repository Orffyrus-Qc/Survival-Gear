# 05 — Current U.S. Brands & How They Work

Focus: brands Americans actually buy for **portable solar generators**, **DIY 12/24/48 V**, and **home backup**. Markets shift yearly; the **architectures** stay stable — learn those.

*Survey snapshot style (mid-2020s U.S. retail / online): not an endorsement ranking.*

---

## 1. Two markets, two architectures

| Market | What you buy | How it works |
|--------|--------------|--------------|
| **Portable Power Station (PPS) / “solar generator”** | One box + optional panel | Battery + BMS + MPPT + inverter integrated |
| **Component DIY / off-grid** | Separate panel, SCC, battery, inverter | You assemble; more repairable and mixable |

Survival skill: use PPS for **speed and safety**; use DIY for **repair, scrap, and scale**.

---

## 2. Portable power station brands (U.S. common)

### EcoFlow

| | |
|--|--|
| **Position** | Feature-heavy, fast AC charging, strong app ecosystem |
| **Architecture** | LiFePO4 on most current lines; internal MPPT; XT60-class solar; expandable official extras on many models |
| **How it works** | Wall/solar/car → multi-input charging → BMS-managed pack → DC outs + pure sine inverter |
| **Learn on it for** | Port discipline, solar Voc limits, expansion branding lock-in |
| **Lines (conceptual)** | River (portable), Delta (mid/large), Pro/Ultra (home backup class) |

### Jackery

| | |
|--|--|
| **Position** | Very common consumer brand; simple UX |
| **Architecture** | Integrated station + SolarSaga panels; proprietary multi-port solar on many units |
| **How it works** | Same PPS block diagram; often emphasized “kit” selling with matched panels |
| **Watch** | Solar port voltage/current and official vs third-party adapters |
| **Best for** | Beginners who want few decisions |

### Bluetti

| | |
|--|--|
| **Position** | Competitive Wh/$, modular expansion on many models |
| **Architecture** | LFP packs common; AC + PV input; some models strong for home backup / capacity stacking |
| **How it works** | Same core PPS design; expansion batteries on brand bus |
| **Learn for** | Capacity planning and modular banks |

### Anker (SOLIX / power house lines)

| | |
|--|--|
| **Position** | Strong retail presence; phone-accessory trust halo |
| **Architecture** | Modern LFP PPS; app; solar input limits like peers |
| **How it works** | Standard integrated chain; emphasis on polished consumer experience |
| **Learn for** | USB-C PD loads + station hybrid use |

### Goal Zero

| | |
|--|--|
| **Position** | Outdoor / adventure retail legacy (Yetis, panels) |
| **Architecture** | PPS + modular boulder/panel ecosystem historically |
| **How it works** | Same energy path; often sold as rugged field kits |
| **Note** | Good mental model for “camp power,” check modern specs per model |

### Others you will see in U.S. listings

| Brand / type | Role |
|--------------|------|
| **Pecron, Oupes, Fanttik, Geneverse, etc.** | Value PPS segment — still same architecture; verify warranty & support |
| **Point Zero Energy, specialized overland** | Niche high-end / vehicle |
| **Generac / home standby (generator + some battery products)** | Home backup, different category than camp PPS |
| **Tesla Powerwall, Enphase, FranklinWH** | Whole-home storage — grid-interactive; not scrap-friendly beginner DIY |

**Mid-knowledge takeaway:** almost every PPS is the same machine in different plastic. Compare **Wh, solar Voc window, continuous inverter W, battery chemistry, expansion, and charge speed**.

---

## 3. DIY / component brands (U.S. common)

### Panels

| Brand / source | Notes |
|----------------|-------|
| **Renogy** | Ubiquitous 12 V RV/van kits, controllers, batteries |
| **Rich Solar, HQST, Newpowa, BougeRV** | Common online rigid/flexible modules |
| **Used residential (Canada/US roof takeoffs)** | High Voc often — need string design + proper MPPT |
| **Harbor Freight / big-box kits** | Entry educational; verify real watts |

### Charge controllers

| Brand | Notes |
|-------|-------|
| **Victron Energy** | Premium, excellent docs, Bluetooth dongles, very common in serious DIY |
| **EPEver / EPsolar** | Popular mid-tier MPPT |
| **Renogy** | Kit-matched PWM/MPPT |
| **Morningstar** | Long-reputation industrial/hobby |
| **Generic PWM** | Fine for small 12 V scrap if limits respected |

### Batteries

| Brand / type | Notes |
|--------------|-------|
| **Battle Born, Renogy, Eco-Worthy, Ampere Time/LiTime, Chins, etc.** | Drop-in 12 V LiFePO4 class widely sold in U.S. |
| **Server rack 48 V (EG4, etc.)** | Home DIY storage trend — higher voltage systems |
| **Odyssey, VMAX, costco AGM** | Lead-acid / AGM still common |
| **Used forklift / golf cart** | Salvage heavy; know flooding and voltage |

### Inverters / inverter-chargers

| Brand | Notes |
|-------|-------|
| **Victron MultiPlus / Quattro** | Inverter + charger, serious off-grid/van |
| **Growatt, EG4, MPP Solar, Sigineer** | Hybrid / AIO popular in DIY home forums |
| **AIMS, Giandel, Bestek** | Common Amazon-class pure/modified sine |
| **Samlex** | Mobile / commercial reputation |

### How DIY chain works (brand-agnostic)

```
Panels (any) 
  → MPPT/PWM (set to battery chemistry)
    → Battery + BMS (LFP) or lead-acid
      → Inverter or DC loads
        → Optional AC charger / generator input on inverter-charger
```

---

## 4. How each architecture “thinks”

### A. Integrated PPS (EcoFlow, Jackery, Bluetti, Anker…)

```
[Panel] --DC--> [Internal MPPT] --charge--> [Cells + BMS] --DC--> [USB/12V]
                                              |
                                              +--> [Inverter] --AC--> outlets
```

- User never wires battery bus.  
- Expansion only if official.  
- Failure mode: unit-level repair hard; treat as field-replaceable module.

### B. Classic off-grid 12/24 V

```
[Panel] --> [SCC] --> [Battery bank] --> [Inverter]
                           |
                           +--> DC fuse panel (lights, radio)
```

- Most educational for survival repair.  
- Scrap-friendly.

### C. Hybrid all-in-one (AIO) wall unit

```
[Panels] --> [AIO hybrid inverter] <--> [Battery]
                    |
                    +--> Home loads / grid sell-back (where legal)
```

- High power, code-heavy, less “camp.”  
- Brand ecosystems (EG4 + matching batteries, etc.) often closed-loop.

### D. Generator hybrid (survival reality)

```
Solar day charge → battery
Gas/propane generator → AC charger or inverter-charger when sun fails
```

Many U.S. households already own a generator; solar reduces fuel burn, doesn’t always replace it.

---

## 5. Feature checklist when comparing U.S. retail units

| Spec | Why |
|------|-----|
| Wh capacity | Runtime |
| LFP vs other | Cycles, thermal behavior |
| Solar max W + Voc | Which thrift panels work |
| UPS / transfer switch time | Fridge / office backup |
| Pass-through charging | Use while plugged in |
| Weight | Real bug-out limit |
| App dependency | Can you run fully offline? |
| Service / warranty in USA | Long-term |

---

## 6. “Most current” learning priority for this project

For **hands-on → mid** in America today:

1. **EcoFlow or similar PPS** — safe integrated solar I/O habits.  
2. **Renogy-class 12 V DIY kit or Victron-class SCC** — understand real components.  
3. **LiFePO4 12 V drop-in with BMS** — modern storage standard for DIY.  
4. **Any pure sine inverter matched to bank** — AC when needed.  
5. **Scrap SLA + PWM** — emergency / learning only (next section).

---

## 7. Brand independence creed

> If the sticker voltage matches and the chemistry profile is correct, the logo can be anything.  
> If the logo matches but Voc is wrong, the logo will not save the controller.

Continue → [`../06_Scrap_Electronics_Build/README.md`](../06_Scrap_Electronics_Build/README.md)
