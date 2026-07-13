# 03 — Auto-Start & ATS (Outage Auto-Ignition Systems)

**Goal:** when utility power fails, the system **starts the engine**, **verifies power quality**, **transfers the house**, then **returns to utility** safely when grid power is stable.

Terms you will hear:

- **Auto-start / automatic start** — controller cranks the engine without you  
- **Auto ignition** — informal phrase for electric-start + automatic cranking (gasoline/NG/LP use spark ignition; diesel uses compression + glow)  
- **ATS** — Automatic Transfer Switch  
- **AMF** — Automatic Mains Failure (controller function)

---

## 1. System blocks

```
[Utility power] ----\
                     \ 
                      [ ATS / Transfer gear ] ---- [ Home loads ]
                     /
[Standby generator] /
       ↑
[Start battery + charger]
       ↑
[Controller: sense utility, crank, warm-up, exercise]
       ↑
[Fuel: NG / propane / diesel]
```

| Block | Job |
|-------|-----|
| Utility voltage sensors | Detect blackout / brownout |
| Generator controller | Crank, monitor oil/temp/Hz/V, alarms |
| Start battery | Cranking amps; float-charged when utility present |
| Engine + alternator | Make 120/240 V 60 Hz |
| ATS | Disconnect utility, connect generator (break-before-make) |
| Exercise scheduler | Weekly run so oil seals and battery stay healthy |

---

## 2. Outage sequence (typical)

1. **Utility fails** (or voltage/frequency out of window).  
2. Controller waits a short **delay** (avoids nuisance starts on blips).  
3. **Crank** engine (multiple attempts with rest).  
4. Engine runs; alternator voltage/frequency stabilize.  
5. Optional **warm-up** delay.  
6. **ATS transfers** loads to generator.  
7. Generator runs under load; controller watches faults (low oil, overspeed, overload).  
8. **Utility returns** and stays stable for a **return delay**.  
9. ATS transfers back to utility.  
10. Generator **cool-down** run, then shutdown.  
11. Start battery returns to charge from utility-powered charger.

If start fails: alarm / app notification (Wi-Fi modules on many Generac/Kohler/Cummins systems). You fall back to manual procedures.

---

## 3. ATS types (mid knowledge)

### Whole-panel ATS

- Switches the entire service (within generator rating)  
- Needs correctly sized standby unit  

### Service-entrance ATS

- Special placement relative to meter/main — **electrician design**  

### Critical-load / managed subpanel

- Only essential breakers on the generator bus  
- Smaller generator, lower cost, smart for Canada heating reality  

### Soft load / load management modules

- Some systems shed big loads (range, dryer, EVSE) automatically so a mid-size gen can cover more of the house  

### Manual transfer (not automatic)

- You start the gen and flip the switch — cheaper, reliable if you are home  

---

## 4. Interlock vs ATS (do not confuse)

| Device | Auto-start? | Auto transfer? | Typical use |
|--------|-------------|----------------|-------------|
| Breaker **interlock** | No | No | Portable + inlet, code-friendlier than illegal backfeed |
| **Manual** transfer switch | No | No | Flip handle after gen is running |
| **ATS** | Usually with standby package | Yes | Unattended outages |

**Never** use a male-to-male “suicide cord” into a dryer outlet.

---

## 5. What “auto ignition system” means in practice

For home standby:

1. **12 V start battery** must be healthy year-round.  
2. **Battery tender / internal charger** needs utility power when grid is up.  
3. **Spark ignition** (gas/LP/NG) or **diesel glow/crank** controlled by ECU.  
4. **Fuel solenoid** opens only when running.  
5. Sensors: oil pressure, coolant temp (liquid-cooled), overspeed, door, etc.

**Weak start battery = #1 reason “auto system failed in the ice storm.”**  
Test/replace on a schedule; keep terminals clean; consider cold-cranking rated batteries in Canada.

---

## 6. Portable generators and “automation”

Possible mid-tier setups (not full standby):

| Setup | Reality |
|-------|---------|
| Electric start + fob | You still connect cords / flip interlock |
| Aftermarket open-transition controllers | Advanced DIY; easy to do wrong — prefer listed kits |
| Inverter + EcoFlow / battery that auto-charges | Battery covers short blips; gen for long outages **manually** |
| Transfer switch with generator-start contacts | Some switches send a start signal to compatible gensets |

For **true unattended home backup**, buy a **listed standby + ATS package** installed to code.

---

## 7. Install & code (Canada-oriented)

- **Electrical:** Canadian Electrical Code (CEC) practice via provincial amendments; permit + licensed electrician.  
- **Québec:** work often under **RBQ** licensing categories; municipal permits.  
- **Gas:** NG/propane train by licensed gas technician; clearances to windows/property lines.  
- **Placement:** exhaust away from doors, windows, fresh-air intakes; CO alarms inside home (required practice).  
- **Bonding/neutral:** generator neutral bonding must match transfer equipment design — wrong bonding = dangerous open neutrals or ground loops.  

This project does **not** replace a licensed design.

---

## 8. Weekly exercise & maintenance (auto systems)

Most standbys **self-start weekly** for ~5–20 minutes.

Your checklist:

- [ ] Exercise runs complete (check app/history)  
- [ ] No fault codes  
- [ ] Oil level / schedule oil changes (hours)  
- [ ] Air filter, spark plugs (spark engines)  
- [ ] Fuel: LP tank level; NG leak checks by pro as needed  
- [ ] Start battery voltage / age (often 2–5 years life)  
- [ ] Clear snow/ice from intake, exhaust, enclosure  
- [ ] Test under real load once per season (fridge + blower)  

---

## 9. Failure modes during outages

| Symptom | Likely cause |
|---------|--------------|
| No crank | Dead start battery, blown fuse, cold oil, bad starter |
| Crank no start | Fuel valve off, empty LP, spark/glow issue, flooded |
| Runs but no house power | ATS not transferring, breaker off, overload trip |
| Transfers then dies | Overload, low oil, fuel starvation |
| Starts on blips too often | Sense delay settings; utility quality |
| CO alarm in house | Exhaust leak / bad placement — shut down, evacuate, fix |

---

## 10. Hands-on drills (without being reckless)

1. Sketch your panel: main breaker, any generator breaker, inlet.  
2. Label critical loads for a future subpanel.  
3. On a portable day: full start, measure voltage with multimeter at receptacle, run a known load.  
4. Replace or load-test a generator start battery before winter.  
5. Read the ATS sequence in your brand manual once — know the LED meanings.

Continue → [`../04_Canadian_Brands_Best_Fit/README.md`](../04_Canadian_Brands_Best_Fit/README.md)
