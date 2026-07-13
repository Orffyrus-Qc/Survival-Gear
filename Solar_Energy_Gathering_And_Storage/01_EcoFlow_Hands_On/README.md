# 01 — EcoFlow: Key Hands-On → Mid Knowledge

EcoFlow is used here as a **teaching platform**: a sealed portable power station (PPS) that combines battery, BMS, charge inputs, and inverter in one chassis. Once you understand EcoFlow, other “solar generators” (Jackery, Bluetti, Anker, Goal Zero, etc.) map easily.

> **Mid knowledge target:** you can explain every port, choose solar that fits Voc/Isc limits, expand capacity correctly, and diagnose common faults without guessing.

---

## 1. What EcoFlow is (architecture)

| Block inside the unit | Job |
|----------------------|-----|
| LiFePO4 (or older NMC on some models) battery pack | Stores energy (Wh rating on the box) |
| BMS (Battery Management System) | Protects cells: overcharge, over-discharge, over-current, temperature |
| AC charger / dual charging | Charges from wall (and sometimes car + AC together) |
| Solar charge input (MPPT) | Converts panel power into safe battery charge |
| Inverter | Battery DC → household AC (pure sine on modern units) |
| DC outputs | USB-A/C, 12 V car socket, sometimes Anderson / extra DC |
| Display / app | State of charge (SoC), input/output watts, faults |

**Key idea:** You do **not** pick a separate charge controller for EcoFlow solar input — the MPPT is **inside**. You only match **panel voltage/current to EcoFlow’s solar input specs**.

---

## 2. Specs that matter (read the sticker / manual)

Before any solar cable goes in, write down for **your** model:

| Spec | Meaning | Why it matters |
|------|---------|----------------|
| Capacity (Wh) | Usable energy roughly | Runtime estimate |
| Battery type | LFP vs NMC | Cycle life, cold-weather rules |
| Max solar input (W) | Ceiling of harvest | Bigger panel field won’t help past this |
| Solar input voltage range (V) | Working window | Too low = no charge; too high = damage risk |
| Max open-circuit voltage Voc | Absolute panel Voc limit | **Most important anti-damage number** |
| Max short-circuit current Isc | Current limit | Overcurrent can trip or damage |
| AC output (W continuous / surge) | What you can run | Motors need surge headroom |
| Charge temperature limits | Cold charge ban | LFP often won’t charge near freezing |

**Example family (approximate — always verify your model):**

- River-class: lower Wh, lower solar W, great for phones/lights/laptop  
- Delta-class: higher Wh, higher solar W, power tools / mini-fridge territory  
- Delta Pro / Ultra class: home-backup scale, often expanders and smart home kits  

*Numbers change by SKU and year. The habit is: open-circuit voltage first, watts second.*

---

## 3. Ports — hands-on identification

### Inputs (energy in)

1. **AC input** — wall charger cable. Often proprietary EcoFlow plug or IEC-style depending on model.  
2. **Solar / car XT60 (or similar)** — many EcoFlows use **XT60** for solar and car charging. Polarity is critical.  
3. **Extra solar or dual PV** on larger units — second MPPT channel; still obey Voc per channel.  
4. **Extra battery / Smart Extra Battery** ports — only EcoFlow-matched expanders for that line.

### Outputs (energy out)

1. **AC outlets** — inverter on. Idle drain exists; turn inverter off when not needed.  
2. **USB-A / USB-C PD** — efficient for phones, tablets, some laptops.  
3. **12 V car socket** — good for fridges designed for 12 V, radios, tire pumps (watch continuous amp draw).  
4. **DC5521 / Anderson** (model-dependent) — higher current DC accessories.

**Survival habit:** Prefer DC and USB over AC inverter when possible — less conversion loss, longer runtime.

---

## 4. First power-up (zero damage)

1. Inspect for dents, liquid, crushed ports.  
2. Charge from **wall** to ~100% once so SoC calibration is sane.  
3. Note fan noise, smell (none is good), and app pairing if used.  
4. Discharge with a small known load (USB light or phone) and confirm Wh / % moves as expected.  
5. Only then introduce solar.

---

## 5. Solar connection — EcoFlow specific order

### Cable path

```
Panel MC4  →  MC4-to-XT60 (or EcoFlow solar cable)  →  EcoFlow XT60 solar port
```

### Rules

1. **Cover the panel** or face it away from sun while mating connectors.  
2. Confirm adapter polarity with multimeter: **red = positive**, black = negative on the station side per manual.  
3. Series vs parallel of panels:
   - **Series** raises voltage (Voc adds) — watch max Voc hard limit.  
   - **Parallel** raises current (Isc adds) — watch max Isc / input current.  
4. Stay **inside** EcoFlow’s voltage window; “almost” over Voc is still a no.  
5. Shade, angle, and dirty glass kill real watts more often than brand choice.

### Safe assembly checklist (solar)

- [ ] Voc of array (coldest expected temp) ≤ unit max Voc  
- [ ] Operating voltage lands in the unit’s MPPT input range  
- [ ] Cable gauge thick enough for current (thin cable = heat = fire risk)  
- [ ] No bare MC4 pins forced into wrong gender adapters  
- [ ] Strain relief so the XT60 isn’t yanked by wind on a tarp camp  

---

## 6. What EcoFlow does for you (and what it doesn’t)

| Does | Does not |
|------|----------|
| Prevents many overcharge/over-discharge faults via BMS | Fix reverse polarity if you force a wrong adapter |
| MPPT harvest from compatible panels | Accept arbitrary high-voltage string panels (roof HV strings) |
| Pure sine AC for sensitive gear (modern units) | Replace a transfer switch / whole-home install by itself (unless kit designed for it) |
| App firmware updates | Make mismatched expanders from other brands work |

---

## 7. Mid-knowledge diagnostics

| Symptom | Likely cause | What to check |
|---------|--------------|---------------|
| 0 W solar, sunny day | Voc too low, cable polarity, covered panel, wrong port | Multimeter at cable end before plug-in |
| Charges then stops early | Over-temp, BMS limit, full SoC | Ambient heat, vents blocked |
| Inverter shuts under load | Overload or surge | Continuous vs surge W; soft-start loads |
| App shows error code | Specific protection trip | Manual error table; reset after cooling |
| Runtime far below Wh rating | Inverter efficiency + idle + Peukert-like behavior | Measure real load watts; use DC when possible |

---

## 8. Hands-on drills (practice)

1. **Port map:** Label a paper sketch of your unit’s ports from memory.  
2. **Load audit:** List 5 survival loads with estimated watts and hours → Wh needed.  
3. **Voc math:** Two 20 V Voc panels in series → 40 V Voc. Is that under your unit’s max?  
4. **Idle tax:** Measure overnight drain with inverter on vs off.  
5. **Cold rule:** Write your battery chemistry and lowest charge temperature.

---

## 9. EcoFlow ecosystem (mid knowledge)

- **Portable Power Station (PPS):** self-contained.  
- **Extra Battery:** capacity only, usually same brand/line.  
- **Smart Home Panel / transfer kits (higher end):** whole-home circuits — not beginner camp gear.  
- **Official solar blankets / rigid panels:** convenient connectors; third-party panels work if Voc/Isc match.  
- **Firmware:** occasional charge-curve and feature fixes — update when stable power is available.

---

## 10. Bridge to the rest of this module

EcoFlow hides the charge controller and battery interconnects. Next sections **open the box conceptually**:

- You will learn to identify a standalone MPPT/PWM controller.  
- You will assemble panel → controller → battery → inverter **in order**.  
- You will mix brands only when electrical rules allow.

Continue → [`../02_Identify_Components/README.md`](../02_Identify_Components/README.md)
