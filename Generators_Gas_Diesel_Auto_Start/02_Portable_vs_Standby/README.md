# 02 — Portable vs Home Standby

Two different tools. Confusing them wastes money and creates unsafe installs.

---

## 1. Side-by-side

| | **Portable** | **Home standby** |
|--|--------------|------------------|
| Location | Wheeled outdoors when needed | Permanent pad beside house |
| Start | Pull cord / electric button / remote | Auto-start on outage (with ATS) |
| Fuel | Gas, diesel, dual-fuel LP | Usually **NG or propane** (some diesel industrial) |
| Hookup | Extension cords or **manual** inlet + interlock/transfer | **ATS** hardwired to panel |
| Cost | Hundreds–few thousand CAD | Many thousands + install |
| Ideal | Cottage, apartment rules (careful), partial loads | Primary residence auto-backup |

---

## 2. Portable classes

### Inverter (quiet, cleaner power)

- Honda EU-class, Yamaha EF, Westinghouse iGen, Generac iQ, etc.  
- Parallel kits on some models for more watts  
- Best for: electronics, charging solar stations, modest fridge

### Open-frame conventional

- Louder, cheaper watts  
- Fine for saws, space heaters, well pumps (if surge allows)  
- Check **starting (surge) watts** vs running watts

### Dual-fuel / tri-fuel wheeled

- Popular “storm kit” in big-box Canada  
- Propane for storage + gasoline for max power

---

## 3. Standby classes

| Size (typical) | Role |
|----------------|------|
| 7–12 kW | Critical circuits: fridge, some lights, boiler/furnace blower, sump, modem |
| 14–22 kW | Larger partial or modest whole home (no big electric heat) |
| 24 kW+ / liquid-cooled | Larger homes, wells, multi-AC, light commercial |

**Electric heat / heat pumps / EV chargers** change the math completely — often **not** whole-home on a small standby.

---

## 4. Sizing without guessing

### List critical loads

| Load | Running W | Starting W (motors) |
|------|-----------|---------------------|
| Fridge | 100–800 | 3–5× run briefly |
| Freezer | similar | similar |
| Furnace / boiler electronics + blower | 100–800 | blower surge |
| Sump pump | 800–1500 | high surge |
| Well pump | often high | very high |
| Lights / router | low | low |
| Microwave | 1000–1500 | — |
| Space heater | 1500 | — |

### Method

1. Sum **running** watts of simultaneous critical loads.  
2. Add the **largest single motor start** margin.  
3. Pick generator continuous rating **above** that; never plan on surge as continuous.  
4. Prefer running at ~50–80% load for efficiency and longevity (especially diesel).

---

## 5. How power gets into the house

### A. Extension cords only (portable)

- Outdoor-rated cords, proper gauge (e.g. 12 AWG for longer 15 A runs)  
- One cord per load or use a **listed** outdoor spider box  
- Never run cords under rugs or through door pinch long-term

### B. Inlet box + manual transfer / interlock (portable or small gen)

```
Generator → power inlet (exterior) → transfer switch OR breaker interlock → selected breakers
```

- **Interlock kit:** physical slide so main utility breaker and generator breaker cannot both be on  
- **Manual transfer switch:** dedicated critical-load subpanel  

### C. Automatic Transfer Switch + standby (auto ignition)

```
Utility ──┐
          ATS ──→ Home panel / critical subpanel
Generator ─┘
```

See section 03 for full auto-start sequence.

---

## 6. Identify components (hands-on)

| Part | What it looks like |
|------|--------------------|
| Generator receptacle L14-30 / 14-50 | Twist-lock or RV-style outlet on gen |
| Power inlet box | Weatherproof male inlet on house exterior |
| Transfer switch | Wall box with utility/gen positions |
| ATS | Often near main panel; contactor + controller |
| Generator controller | LCD/buttons on standby unit |
| Battery (standby) | 12 V start battery in unit — maintain it |

---

## 7. Portable “auto start”?

Some portables offer **electric start + remote fob** or app. That is **not** the same as a home ATS system:

| Feature | Portable remote start | True standby auto-start |
|---------|----------------------|-------------------------|
| Detects grid failure | Rarely | Yes |
| Transfers house loads | No (you still cord/inlet) | Yes via ATS |
| Weekly self-test | Rare | Common |
| Unattended multi-day | Poor (fuel, CO, weather) | Designed for it |

---

## 8. Canada / cottage realities

- **Cottages:** dual-fuel portable + manual inlet often best ROI  
- **Primary home, ice storms, medical devices:** standby NG/LP + ATS  
- **Apartments / condos:** balconies often **forbid** generators (CO + bylaws) — use battery stations instead  
- **Noise bylaws** still exist during non-emergency use  

Continue → [`../03_Auto_Start_ATS_Outage/README.md`](../03_Auto_Start_ATS_Outage/README.md)
