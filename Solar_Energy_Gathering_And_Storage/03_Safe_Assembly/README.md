# 03 — Safe Assembly (Without Damaging Material)

Most DIY solar damage is not “mystery electronics.” It is **wrong order**, **wrong polarity**, **over-voltage**, or **missing fuses**. This section is the muscle memory that protects panels, controllers, batteries, and you.

---

## 1. Golden rules (memorize)

1. **Battery first, panels last** for standalone charge controllers.  
2. **Polarity every time** — multimeter before permanent crimps.  
3. **Fuse at battery positive** before long cable runs.  
4. **Voc under controller/station max** (use cold-temperature Voc estimate for series strings).  
5. **Match system voltage** — 12 V battery with 12 V controller/inverter settings.  
6. **One chemistry, one charge profile.**  
7. **Cover panels** while making first connections.  
8. **No live cable twisting** as a permanent joint — crimp, lug, or proper connector.  
9. **Strain-relief** every connector.  
10. **If unsure, stop** — measure again; don’t “try it and see” on lithium.

---

## 2. Correct connect order (standalone DIY)

### Power-up (first build or reconnection)

```
1. Mount / secure battery in ventilated area (lead-acid vents hydrogen)
2. Install fuse holder on BATTERY POSITIVE (fuse out or open)
3. Connect charge controller BAT+ / BAT− to battery (correct polarity)
4. Insert fuse / close breaker — controller boots, shows battery V
5. Set battery type (SLA / AGM / LFP) on controller if menu exists
6. Connect panels to PV+ / PV− (covered or dark first)
7. Uncover panels — confirm charging amps/watts
8. Only then connect inverter or DC loads (on their own fused lines)
```

### Power-down / service order

```
1. Cover panels or open PV breaker
2. Disconnect PV from controller
3. Turn off loads / inverter
4. Open battery fuse/breaker
5. Disconnect controller from battery if needed
```

### Why battery-before-panel?

Many PWM/MPPT units use battery voltage as their logic supply and reference. Panels alone can put the controller into a bad state and **destroy it**.

---

## 3. Portable power station order (EcoFlow-class)

```
1. Unit OFF or idle as manual says
2. Verify solar cable polarity with meter
3. Cover panel
4. Plug solar cable into station solar port
5. Uncover panel / aim at sun
6. Confirm input watts on display
```

For wall charging: use stock AC cable; avoid damaged plugs; keep vents clear.

---

## 4. Polarity — damage patterns

| Mistake | Common result |
|---------|---------------|
| Reverse battery to controller | Blown controller, melted traces, dead unit |
| Reverse panel | No charge, possible diode/controller stress |
| Reverse inverter | Instant damage or spark; fire risk |
| Wrong XT60 gender adapters “forced” | Reverse polarity into EcoFlow/Jackery-class ports |

**Habit:** red = positive, black = negative — but **always verify** salvaged cables; colors lie.

---

## 5. Mechanical assembly without damage

### Panels

- Support the frame; do not step on glass.  
- Do not overtighten roof mounts into thin frames (cracks cells internally).  
- Flexible panels: no sharp fold; back adhesive needs clean, flat surface.  
- MC4: click until locked; use proper unlock tool — prying with knife damages seals.

### Controllers

- Heat-sink needs air; don’t bury in foam.  
- Terminal screws: snug, not stripped — use ring lugs sized for stud.  
- Keep battery sense wires short and direct when the manual requires it.

### Batteries

- SLA: upright if design requires; no sparks near vents.  
- LiFePO4: mount to protect BMS board from crush; follow manufacturer orientation if specified.  
- Never hammer lugs onto soft posts; use correct post adapters.

### Wire work

- Strip only enough insulation.  
- Crimp with a real crimper; tug-test every lug.  
- Heat-shrink over crimp.  
- Avoid aluminum wire for small DIY unless you know AL rules.  
- Keep battery cables short and heavy for inverters.

---

## 6. Electrical assembly without damage

### Voltage matching

| Battery bank | Panel / controller notes |
|--------------|--------------------------|
| 12 V | Common for scrap & camp; many panels are “12 V nominal” (~18 Vmp) |
| 24 V | Series two 12 V batteries; controller must be 24 V capable |
| 48 V | More efficient for larger systems; higher shock/arc risk |

### Series vs parallel panels

- **Series:** voltages add, current stays ~same → good for MPPT input window; watch Voc.  
- **Parallel:** currents add, voltage stays ~same → thicker cable, fusing per string best practice.  
- Mixed wattage in series: weakest current limits string (mid knowledge).  
- Mixed wattage in parallel: voltages should be similar (Vmp close).

### Controller current sizing

Example: 200 W panel into 12 V battery ≈ 200 / 12 ≈ 16.7 A → pick controller **≥ 20 A** with margin (and real sun may differ).

### Inverter

- Fuse between battery and inverter (both poles ideally on larger systems; at least +).  
- Chassis ground per manual when available.  
- Don’t parallel random inverters without designed paralleling ports.

---

## 7. Protection sizing (practical)

Rule of thumb (verify with charts for length/ampacity):

1. Find max continuous current of the cable run.  
2. Fuse ≤ cable ampacity, ≥ continuous load (or use manufacturer table).  
3. Place fuse near source of energy (battery + for load side; PV string fuses when paralleling).  

Undersized wire + oversized fuse = **fire with a working fuse**.

---

## 8. Environment & survival mounting

- Keep electronics dry; condensation kills boards.  
- Shade the controller and battery if ambient is hot; heat shortens life.  
- Ventilate lead-acid.  
- Secure batteries so they cannot short against metal truck beds.  
- Strain-relieve panel leads so wind doesn’t fatigue MC4 joints.

---

## 9. First-power test protocol (no damage)

1. Visual inspection — frays, reverse colors, loose strands near terminals.  
2. Continuity: fuse is good; no short between BAT+ and BAT− with loads off.  
3. Battery voltage alone — healthy range for chemistry.  
4. Controller on battery only — settings correct.  
5. Panel Voc measured **disconnected**.  
6. Connect PV, confirm charge current is sane (not maxed in a fault).  
7. Add small DC load; watch battery voltage stay stable.  
8. Inverter last with a known small AC load (lamp), then real loads.

---

## 10. Common damage scenarios (avoid these)

| Scenario | Prevention |
|----------|------------|
| Controller connected to PV before battery | Battery first always |
| Series string Voc 60 V into 50 V max MPPT | Voc math + cold factor |
| LFP charged with lead-acid-only profile forever | Set Li / correct V |
| Parallel old SLA with new SLA | Match age/capacity or use separate buses carefully |
| Inverter cables 16 AWG on 1000 W | Size wire for current |
| Metal tool bridges battery posts | Cover posts; one tool discipline |
| Water in MC4 | Quality connectors, drip loops |

---

## 11. Assembly checklist (print / copy)

- [ ] Chemistry identified  
- [ ] System voltage chosen (12/24/48)  
- [ ] Controller supports chemistry + voltage  
- [ ] Voc array ≤ controller/station max  
- [ ] Controller charge amps ≥ expected with margin  
- [ ] Fuse at battery + installed  
- [ ] Wire gauge adequate  
- [ ] Polarity verified  
- [ ] Battery → controller → panel order  
- [ ] Settings saved  
- [ ] Heat and weather protection  
- [ ] Document voltages in a notebook  

Continue → [`../04_Mixed_Brand_Systems/README.md`](../04_Mixed_Brand_Systems/README.md)
