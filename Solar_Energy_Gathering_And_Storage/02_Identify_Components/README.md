# 02 — Identify Components

If you can **name it, measure it, and read its limits**, you can assemble or salvage without guessing.

---

## 1. The five blocks (every system)

| # | Component | One-line job | Typical look |
|---|-----------|--------------|--------------|
| 1 | Solar panel (PV module) | Light → DC electricity | Glass rectangle, blue/black cells, junction box, MC4 leads |
| 2 | Charge controller | Safe charging of battery from panel | Small aluminum box with terminals: PV+, PV−, BAT+, BAT−, sometimes LOAD |
| 3 | Battery | Stores energy | Heavy block (SLA) or rectangular LiFePO4 with BMS leads |
| 4 | Inverter | DC → AC | Box with battery cables + wall outlets |
| 5 | Protection & wiring | Stop fires, allow disconnect | Fuses, breakers, disconnects, cable, lugs |

**Integrated “solar generator”** = 2 + 3 + 4 + BMS in one case (EcoFlow etc.).

---

## 2. Solar panel — how to identify

### Visual

- Front: grid of cells under glass or polymer  
- Back: label (nameplate), junction box, two cables  
- Connectors: usually **MC4** (cylindrical lock; + and − genders differ)

### Nameplate fields (learn these)

| Label | Meaning |
|-------|---------|
| Pmax / Watt | Rated power under standard test conditions |
| Vmp | Voltage at max power (operating, roughly) |
| Imp | Current at max power |
| Voc | Open-circuit voltage (no load — highest voltage) |
| Isc | Short-circuit current (highest current) |
| Cells / type | Mono, poly, flexible thin-film |

### Multimeter checks

1. **Voc:** sun on panel, measure between + and − (careful, can be 20–50+ V).  
2. **Polarity:** red probe on supposed +, black on − → positive reading.  
3. Do **not** short Isc for fun on large panels — sparks and heat.

### Survival salvage clues

- RV roofs, garden lights (tiny), broken street signs, thrift “solar kits,” farm electric fence energizer panels.  
- Cracked glass still can produce power but is weather-risky and lower output.

---

## 3. Charge controller — PWM vs MPPT

### How to recognize

- Terminals labeled **SOLAR / PV** and **BATTERY** (sometimes **LOAD**).  
- Display showing battery voltage, charging amps, mode.  
- Cheap blue/black boxes = often **PWM**. Larger heatsink / higher $ = often **MPPT**.

### PWM vs MPPT (mid knowledge)

| | PWM | MPPT |
|--|-----|------|
| Cost | Lower | Higher |
| Efficiency | Lower when panel V >> battery V | Higher; tracks max power |
| Panel matching | Panel V should be close to battery charge V | Wider panel voltage window |
| Typical use | Small 12 V kits, scrap builds | Mixed panels, higher power |

### Critical label numbers

- Battery system voltage: 12 / 24 / 48 V (auto or set)  
- Max PV input voltage (Voc limit)  
- Max charge current (A)  
- Supported chemistries: sealed, gel, flooded, LiFePO4  

**Damage habit to unlearn:** never power a controller from panels alone with battery disconnected (many designs require battery first).

---

## 4. Battery — identify chemistry before anything else

### Common types you will meet

| Type | Visual / clues | Nominal V (12 V class) | Charge care |
|------|----------------|------------------------|-------------|
| Flooded lead-acid | Caps to add water, heavy | ~12.0–12.7 rest | Ventilate; don’t seal gas |
| AGM / Gel SLA | Sealed, “maintenance free” | ~12.0–12.8 rest | Correct AGM/gel profile |
| LiFePO4 (LFP) | Often Bluetooth BMS, lighter Wh/kg | ~12.8 (4s) | Needs LFP charge voltage; BMS required |
| NMC / laptop cells | Cylindrical 18650 packs, tool packs | Varies | **Advanced only** — fire risk if abused |

### Resting voltage rough map (12 V lead-acid)

| Rest V | Rough state |
|--------|-------------|
| ~12.7+ | Full |
| ~12.2 | ~50% |
| ~11.9 or less | Low — stop discharging |

LiFePO4 sits near **13.2–13.4** when full and drops steeply near empty — SoC vs voltage is flatter; trust BMS % when available.

### Never mix in one series/parallel string without design

- Different chemistries  
- Very different ages or Ah ratings  
- One weak battery will drag or overstress others  

---

## 5. Inverter — identify and size

| Label | Meaning |
|-------|---------|
| Continuous watts | What it can run all day |
| Surge watts | Short motor start |
| Input voltage | 12 / 24 / 48 V must match battery bank |
| Waveform | Modified sine (cheap) vs pure sine (better for electronics) |
| Efficiency | Often 85–95%; rest becomes heat |

**Clue:** cigarette-plug inverters are usually small continuous W and thin wire — camping phone/laptop only, not power tools.

---

## 6. Protection parts — identify

| Part | Job | How to spot |
|------|-----|-------------|
| ANL / MEGA / MIDI fuse | High DC current protection | Metal strip fuse in holder near battery + |
| Blade fuse (ATO) | Lower current branch | Car-style fuse box |
| DC breaker | Protection + disconnect | Toggle switch with amp rating |
| Blocking diode | Prevent reverse night current (sometimes built into controller) | In-line diode module |
| Bus bar | Clean multi-cable join | Copper bar with studs |

**Rule:** fuse **as close to battery positive** as practical, sized for the **wire**, not “whatever fits.”

---

## 7. Connectors & wire — identify

| Connector | Common use |
|-----------|------------|
| MC4 | Panel strings |
| XT60 / XT90 | Portable stations, high-current DC |
| Anderson SB / Powerpole | Winches, DIY DC, some stations |
| Ring / fork lugs | Battery and inverter studs |
| Barrel DC5521 | Accessory DC on some stations |
| SAE 2-pin | Solar maintainers, some kits |

Wire: thicker = lower gauge number in AWG (e.g. 8 AWG thicker than 14 AWG). Undersized wire overheats.

---

## 8. Multimeter field kit skills

Practice until automatic:

1. **DC voltage** — battery and panel Voc  
2. **Continuity / resistance** — cable integrity, fuse not open  
3. **Polarity** — before every first connection  
4. (Optional mid) **DC current** — only with proper shunt or clamp meter; series ammeter misuse blows meters  

---

## 9. Identification drill (scrap pile)

For any unknown box:

1. Photo the labels.  
2. Note input/output voltage printed.  
3. Is it PV, battery, AC, or data?  
4. If no label and no datasheet — **do not** connect to expensive batteries; bench-test isolated with care or discard for structural scrap only.

---

## 10. Quick ID flowchart

```
Has glass cells + two DC leads? → PANEL
Has PV + BAT terminals, ~12–48 V? → CONTROLLER
Heavy, two big posts, 12 V class? → BATTERY (check chemistry label)
Wall outlets on a DC-fed box? → INVERTER
Sits on battery + cable? → FUSE / BREAKER
All-in-one with LCD + AC + solar port? → PORTABLE POWER STATION
```

Continue → [`../03_Safe_Assembly/README.md`](../03_Safe_Assembly/README.md)
