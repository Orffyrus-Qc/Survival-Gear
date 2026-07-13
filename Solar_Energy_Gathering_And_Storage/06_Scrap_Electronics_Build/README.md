# 06 — Build a Basic System from Scrap Electronics

**Goal:** a working **12 V solar → controller → battery → light/USB** system using scavenged or thrift parts, with rules that keep you from starting fires.

This is **survival education**, not a code-compliant house install.

---

## 1. Scope of the “basic scrap system”

### Target system

| Block | Target for beginners |
|-------|----------------------|
| Voltage | **12 V only** |
| Panel | 20–100 W scavenged or thrift |
| Controller | Cheap PWM 10–30 A with LED/display |
| Battery | **Sealed lead-acid (SLA/AGM) 7–100 Ah** preferred for scrap learning |
| Output | 12 V LED lights, phone via USB buck converter, optional small inverter later |
| Not in v1 | Series high-voltage strings, scrap laptop Li-ion packs, grid tie |

### Why SLA first for scrap?

- Forgiving of imperfect charge settings vs raw lithium cells  
- Common in UPS units, alarms, mobility scooters, toys  
- Visible failure modes (swelling — retire it)  
- Still needs ventilation awareness and correct polarity  

**LiFePO4 drop-in** is excellent when **known good with BMS** — treat as “known component,” not mystery scrap cells.

---

## 2. Safety non-negotiables (scrap)

1. Eye protection when working on batteries.  
2. Fuse on battery positive — always.  
3. No jewelry on hands when on battery posts.  
4. No charging scrap lithium pouch packs without proper BMS and knowledge.  
5. Assume salvaged wire insulation is damaged until inspected.  
6. Work outdoors or on non-flammable surface first power-up.  
7. Keep a disconnect (switch or pull fuse) you can reach fast.  
8. If battery is hot, bulging, or smells — **isolate outdoors, end of life**.

---

## 3. Where to scavenge (U.S. realistic)

| Source | What you get | Watch for |
|--------|--------------|-----------|
| Dead UPS (APC etc.) | 12 V SLA, sometimes wiring | Pack may be sulfated |
| Alarm panels / exit lights | Small SLA | Low Ah |
| Mobility scooter / kids ride-on | 12 V batteries, chargers | Chargers may be dumb |
| RV salvage / trailers | Panels, wiring, controllers | Weather damage |
| Garden solar lights | Tiny panels (toy power only) | Education micro-voltage |
| Thrift / Facebook Marketplace | Panels, “solar kits,” inverters | Fake watt labels |
| Auto wrecking (knowledgeable) | Wire, fuses, lugs — not usually panels | Lead-acid starter ≠ deep cycle |
| E-waste (advanced) | PSU diodes, buck modules, XT60 | Only if you can identify parts |
| Electric fence / farm stores used | Small panels | Junction box rot |

### Treasure labels

- `12V 7Ah`, `12V 18Ah`, `12V 35Ah` SLA  
- `PWM 20A`, `MPPT 30A` with PV and BAT terminals  
- Panel stickers with Voc / Vmp  
- `DC-DC 12V to 5V` USB modules  
- Inline ANL/blade fuse holders  

### Leave it / advanced only

- Swollen Li-ion pouches  
- Loose 18650s with no protection  
- High-voltage server PSUs without isolation knowledge  
- Microwave capacitors, CRT gear  

---

## 4. Parts list — minimum viable scrap solar

| Qty | Part | Spec |
|-----|------|------|
| 1 | Solar panel | “12 V nominal” ≈ 17–22 V Voc typical for small modules |
| 1 | PWM controller | ≥ 10 A; battery type selectable if possible |
| 1 | 12 V SLA/AGM | Start 7–20 Ah for learning; larger if loads demand |
| 1 | Fuse + holder | e.g. 10–30 A depending on wire/controller |
| Wire | Red/black | Short runs 12–14 AWG for small systems; thicker if longer/higher A |
| 1 | 12 V LED strip or bulb | Known ~1–5 A max for first test |
| 1 | Multimeter | Required |
| Optional | USB buck 12 V→5 V | Phone charge |
| Optional | Small pure sine inverter | Only after DC works; fuse heavily |
| Optional | MC4 connectors | Replace cut-off panel leads |

---

## 5. Identify & test scrap before assembly

### Panel

1. Clean glass.  
2. In sun, measure **Voc** (should be roughly in teens–20s V for 12 V class).  
3. If Voc near 0 in full sun → dead panel or open diode/junction.  
4. Note polarity with meter.

### Battery

1. Measure rest voltage.  
   - ~12.0–12.8 V range may be usable.  
   - ~10 V or less often sulfated/dead for SLA.  
2. Inspect case for cracks/swelling.  
3. Clean posts.  
4. If you have a known good charger, slow charge and see if it holds voltage after rest.

### Controller

1. No burnt smell / scorch marks.  
2. Terminals labeled.  
3. Power from **battery only** first — display should show ~12 V.  
4. If it only runs when panels connected and battery absent — beware; follow battery-first rule anyway.

### USB / buck modules

1. Apply 12 V carefully; confirm 5 V output before phone.  
2. Prefer modules with USB port and CC/CV phone-oriented design.

---

## 6. Wiring diagram (basic)

```
                    [SOLAR PANEL]
                     +        -
                     |        |
                     |        |
                  PV+      PV-   (on controller)
                     |        |
              +------+--------+------+
              |   CHARGE CONTROLLER  |
              |   (PWM or MPPT)      |
              +------+--------+------+
                  BAT+     BAT-
                     |        |
                    [FUSE]    |
                     |        |
                     +--[12V BATTERY]--+
                     |                 |
                     +----(loads)------+
                           |
                    [LED / USB buck]
```

**Optional later:**

```
BAT+ --[FUSE]-- INVERTER+ 
BAT- ---------- INVERTER-
INVERTER outlets → carefully chosen AC loads only
```

---

## 7. Assembly steps (scrap build)

### Step 1 — Mechanical layout

- Board, plastic tote (non-sealed if lead-acid venting), or ammo-can with isolation.  
- Battery secured so it cannot slide and short.  
- Controller mounted with airflow.

### Step 2 — Battery → fuse → controller

1. Install fuse holder within inches of BAT+.  
2. Connect controller BAT− to battery −.  
3. Connect controller BAT+ to fuse to battery +.  
4. Insert correct fuse.  
5. Confirm controller display / LED shows battery voltage.  
6. Set **sealed / AGM** mode if available (not Li unless battery is LFP).

### Step 3 — Panel → controller

1. Cover panel.  
2. Connect PV− then PV+ (or per manual) with correct polarity.  
3. Uncover; confirm charging indication.  
4. Multimeter: battery voltage should rise slowly under sun with load off.

### Step 4 — DC load

1. Wire LED through its own small fuse if possible.  
2. Prefer controller **LOAD** terminals only if manual allows and current is small; many people wire loads to battery via separate fuse block for clarity.  
3. Lights on — success criterion #1.

### Step 5 — USB

1. Buck module input to fused 12 V.  
2. Verify 5 V.  
3. Then phone.

### Step 6 — Document

Write Voc, battery V full/empty habits, fuse sizes in a card taped to the tote.

---

## 8. Scrap “recipes”

### Recipe A — UPS resurrection (tabletop)

- Steal 12 V 7–9 Ah from dead UPS (recycle UPS electronics responsibly).  
- 20–40 W thrift panel.  
- 10 A PWM.  
- LED puck lights.  

**Use:** night light, radio, phone trickle in outage.

### Recipe B — Scooter battery camp box

- 12 V 20–35 Ah mobility battery (if healthy).  
- 50–100 W panel.  
- 20 A PWM/MPPT.  
- Fuse 20–30 A.  
- Optional 150–300 W inverter for laptop briefly.

### Recipe C — Dual panel parallel

- Two similar Voc panels, parallel via MC4 branch, single controller.  
- Fuse each panel if > small toy size (best practice).  
- Controller amps ≥ sum of Imp with margin.

### Recipe D — Not recommended as first scrap

- Parallel random tool batteries.  
- Series laptop packs for 3S/4S without BMS.  
- Direct panel-to-battery with only a diode (no proper control) except tiny educational demos you accept risk on throwaway SLA.

---

## 9. Charge without a fancy controller? (emergency only)

**Diode + panel → SLA** is old-school emergency:

- Panel Voc not wildly above battery  
- Current small  
- You disconnect when full (watch voltage ~14.4 V then stop)  

This is easy to overcharge. Prefer **any** working PWM found in kits.

Car alternator regulators and random wall warts are **not** solar controllers.

---

## 10. What scrap electronics teach mid-level skills

| Skill | How scrap teaches it |
|-------|----------------------|
| Polarity discipline | Wrong UPS wiring sparks once — you learn forever |
| Voltage literacy | Meter becomes automatic |
| Fuse culture | You size for wire you found |
| Accepting losses | Dirty used panels still “work” at 40–70% |
| Repair mindset | Swap PWM for $15 instead of binning whole EcoFlow |

---

## 11. Upgrade path (scrap → solid)

1. Basic PWM + SLA box works.  
2. Replace SLA with **known** 12 V LiFePO4 + set controller to LFP.  
3. Replace PWM with Victron/EPEver-class MPPT when panels grow.  
4. Add fuse block and bus bars.  
5. Add pure sine inverter on short fat cables.  
6. Keep EcoFlow-class PPS as **clean portable** frontline; scrap box as **backup / trainer / stationary**.

---

## 12. First-light success criteria

- [ ] Controller shows battery V with panel covered  
- [ ] In sun, charge amps or “charging” LED active  
- [ ] Battery V rises over 30–60 min sun (load off)  
- [ ] LED load runs from battery after sunset  
- [ ] No component too hot to touch  
- [ ] Fuses only open on real faults, not normal operation  

---

## 13. Ethical & legal notes

- Respect property; scavenge only abandoned / owned / purchased e-waste.  
- Recycle lead-acid properly — lead is toxic.  
- Don’t backfeed home outlets from inverters (islanding hazard).  
- HOA/grid rules don’t apply to a tote in your garage; they do apply to roof ties.

---

## 14. Troubleshooting scrap builds

| Problem | Checks |
|---------|--------|
| No charge | Voc, polarity, blown controller, night, shade |
| Controller blank | Battery fuse, battery dead, reverse polarity damage |
| Battery never rises | Huge load, dead cell, panel too small, bad connection resistance |
| Melting smell | Overcurrent, undersized wire — shut down |
| Phone won’t charge | Buck module noise/current limit; try wall USB for compare |

---

Back to module home → [`../README.md`](../README.md)  
Reference sheets → [`../reference/`](../reference/)
