# Solar Energy Gathering & Storage

**Level:** key hands-on → mid knowledge  
**Start brand (integrated learning):** EcoFlow  
**Goal:** understand how solar is gathered, controlled, stored, and used — including mixed brands and scrap builds.

**Version française :** [`../fr/Solar_Energy_Gathering_And_Storage/README.md`](../fr/Solar_Energy_Gathering_And_Storage/README.md)

## What you will be able to do

After working through this module:

1. Power and charge an EcoFlow-class portable station from wall and solar without damaging ports or cables.
2. Identify panel, charge controller, battery, inverter, fuse, and meter by look and by multimeter.
3. Wire a basic off-grid chain in the **correct order** so controllers and batteries survive.
4. Decide when mixed panels / controllers / batteries / brands are safe — and when they are not.
5. Compare major U.S.-available solar generator and DIY brands by architecture, not marketing.
6. Assemble a **basic 12 V scrap solar system** with scavenged parts and clear safety limits.

## Study order

| # | Folder | Topic |
|---|--------|--------|
| 01 | [`01_EcoFlow_Hands_On/`](./01_EcoFlow_Hands_On/) | EcoFlow from unbox to solar input, ports, limits |
| 02 | [`02_Identify_Components/`](./02_Identify_Components/) | How to recognize each part and read its labels |
| 03 | [`03_Safe_Assembly/`](./03_Safe_Assembly/) | Connect order, polarity, torque, no-damage habits |
| 04 | [`04_Mixed_Brand_Systems/`](./04_Mixed_Brand_Systems/) | Different panel + controller + battery + brand |
| 05 | [`05_US_Brands_How_They_Work/`](./05_US_Brands_How_They_Work/) | Current U.S. brands & architectures |
| 06 | [`06_Scrap_Electronics_Build/`](./06_Scrap_Electronics_Build/) | Basic system from scrap / salvage |
| — | [`reference/`](./reference/) | Spec cheat sheets, connector types, glossary |

## Core energy path (memorize this)

```
SUNLIGHT
   ↓
SOLAR PANEL(S)  →  (DC, variable voltage)
   ↓
CHARGE CONTROLLER  (PWM or MPPT)  →  regulates charge into battery
   ↓
BATTERY  (storage)
   ↓
INVERTER (optional)  →  AC for household plugs
   and/or
DC LOADS  (lights, 12 V devices, USB converters)
```

**Integrated units (EcoFlow, Jackery, Bluetti, Anker, etc.)** put controller + battery + inverter + BMS in one box.  
**DIY / scrap systems** use separate boxes for each block — more flexible, more ways to make mistakes.

## Quick start (today)

1. Read **01_EcoFlow_Hands_On** even if you only own a different brand — the port logic is similar.
2. Practice **02** with any old wall-wart, car battery, or thrift-store panel if you have them.
3. Do **not** jump to scrap lithium packs until you finish 03 and 04.

## Tools you need for mid knowledge

| Tool | Why |
|------|-----|
| Digital multimeter (DC V, continuity) | Confirm voltage and polarity before connecting |
| MC4-compatible connectors / adapter kit | Safe panel connections (no bare twisted wire in rain) |
| Inline fuse holders + correct-amp fuses | Protect cables and batteries |
| Wire strippers, crimper, heat-shrink | Mechanical reliability |
| Alligator leads (fused if possible) | Temporary test hooks only |
| PPE: safety glasses, insulated gloves for higher energy | Eyes and hands |

## Survival context

In field or grid-down use, prioritize:

1. **Charge reliability** over peak watts  
2. **Known battery chemistry** over “mystery high capacity”  
3. **Redundant small systems** over one fragile mega-station  
4. **12 V DC lighting and radios** before large AC inverters (inverters waste energy and add failure points)

For multi-day winter outages, surge loads, and unattended homes, pair this module with  
[`../Generators_Gas_Diesel_Auto_Start/`](../Generators_Gas_Diesel_Auto_Start/) (gas/diesel/propane, auto-start ATS, Canadian brand fit).

---

Next: open [`01_EcoFlow_Hands_On/README.md`](./01_EcoFlow_Hands_On/README.md)
