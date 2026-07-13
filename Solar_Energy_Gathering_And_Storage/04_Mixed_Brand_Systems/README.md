# 04 — Mixed Brand Systems

**Panels, controllers, batteries, and brands do not need to match by logo.**  
They need to match by **electrical limits, chemistry, and communication (if any).**

This is the core mid-knowledge skill for survival: you will rarely find a perfect matched kit in the field or thrift stream.

---

## 1. The hierarchy of compatibility

```
1. SYSTEM VOLTAGE     (12 / 24 / 48 V)     — hard rule
2. CHEMISTRY          (lead vs LFP vs other) — hard rule for charging
3. VOLTAGE LIMITS     (Voc, charge V, cutoffs) — hard rule
4. CURRENT LIMITS     (controller A, wire, BMS) — hard rule
5. CONNECTORS         (adapters OK if polarity correct) — soft
6. BRAND / APP / BUS  (CAN, proprietary expanders) — only when required
```

**Brand is last.** Voltage and chemistry are first.

---

## 2. Mixed solar panels

### Same brand not required

Any crystalline panel can feed a charge controller if:

- Array **Voc** ≤ controller max PV voltage  
- Array current ≤ controller max (with margin)  
- Wiring and fusing are sane  

### Series mixing

- Currents should be similar (Imp of modules close).  
- Weak / shaded / low-Imp panel limits the whole string.  
- Voltages add → easy to exceed Voc limit.

### Parallel mixing

- **Vmp should be similar** (within a few volts ideal).  
- A much higher-voltage panel can backfeed / fight a lower one; use separate controllers or careful design.  
- Each parallel string should be fused when multiple strings.

### Different tech

| Mix | Notes |
|-----|-------|
| Mono + poly | Usually OK if Vmp/Imp close |
| Rigid + flexible | OK electrically if ratings match; flexible ages faster |
| Tiny 5–20 W + large 100 W+ same controller | Works but small panel contribution is minor; still count Voc if series |
| High-voltage grid-tie panel (Voc 40–50 V+) into 12 V PWM | Poor match; prefer MPPT or reconfigure |

### Portable station note

EcoFlow / Bluetti / Jackery / Anker accept third-party panels. Match **input voltage range and connector polarity**, not brand of glass.

---

## 3. Mixed charge controllers

### One controller per battery bank is simplest

Beginner / mid rule:

- **One** smart charging brain (controller or PPS) in charge of a given battery bank.  
- Two uncoordinated chargers can argue over voltage (possible overcharge risk depending on designs).

### When two controllers appear

| Situation | Approach |
|-----------|----------|
| Two panel arrays far apart | Two MPPTs both set to **same** chemistry/voltage profile into **one** bank is common DIY practice — set identical absorb/float/LFP targets |
| Solar + alternator + wall | Use devices designed for multi-input or known combiner patterns |
| EcoFlow + external controller into same DIY battery | Don’t freestyle; either use station as the system or DIY bank — avoid fighting BMS profiles |

### PWM brand A + battery brand B

Fine. Set the **battery type menu** to match battery chemistry, not panel brand.

### MPPT brand C + panels brand D

Fine. Size for Voc and watts.

---

## 4. Mixed batteries (high caution)

### Do not casually mix

| Mix | Verdict |
|-----|---------|
| New + very old same chemistry parallel | Poor — old unit may reverse charge / overheat |
| Different Ah in parallel | Possible if same chemistry, same voltage, similar age/health; currents share unevenly |
| Different Ah in series | **No** — weak unit over-discharges |
| Lead-acid parallel with LiFePO4 | **No** on same string |
| Different brand LiFePO4 same voltage with BMS | Parallel sometimes OK if voltages match and manuals allow; series of different BMS packs is advanced |
| Starter car battery as solar bank | Short-cycle life; emergency only |

### Safe mixed-brand battery patterns

1. **Same chemistry, same nominal voltage, similar capacity & age**, parallel with equal cable lengths.  
2. **Separate batteries, separate controllers, separate loads** — then you are not “mixing,” you have two systems.  
3. **Known brand LFP with documented charge voltage** charged by any quality MPPT that supports LFP profile.

### Portable expanders

EcoFlow extra batteries, Bluetti expansion batteries, etc. are **proprietary** electrically/communication-wise.  
**Different brand expanders will not plug in.** That is the main place brand **does** matter.

---

## 5. Mixed inverters

- Inverter input V must match battery bank V.  
- Brand irrelevant for pure conversion.  
- Grounding and GFCI behavior differ — read manual for fixed installs.  
- Do not stack AC outputs of two random inverters onto one outlet.

---

## 6. Decision matrix — “Can I connect this?”

### Panel → Controller / PPS

| Check | Pass if |
|-------|---------|
| Voc_array | ≤ max PV input |
| Vmp / operating V | Inside MPPT range (or sensible for PWM) |
| Isc / Imp | ≤ input current limit |
| Connector | Adapter exists, polarity verified |

### Controller → Battery

| Check | Pass if |
|-------|---------|
| System V | Controller set to 12/24/48 correctly |
| Charge voltage | Matches chemistry (e.g. LFP ~14.2–14.6 absorb typical — **use battery maker values**) |
| Charge current | ≤ battery max charge A (LFP often 0.5C unless specified) |
| Temperature | Within charge limits |

### Battery → Inverter / load

| Check | Pass if |
|-------|---------|
| Voltage | Match |
| Continuous current | BMS and cables support inverter draw |
| Fuse | Present and sized |
| Low-voltage cutoff | Prevents brick dead battery |

---

## 7. Example mixed systems (realistic)

### Example A — camp “franken system”

- Used 100 W Renogy-style panel  
- Generic 20 A PWM from marketplace  
- Costco/weigh-style 100 Ah LiFePO4 (any solid brand with BMS)  
- Old 300 W pure sine inverter  

**OK if:** PWM has Li mode or correct voltage, Voc panel ~22 V under 50 V limit, fuses present.

### Example B — EcoFlow + thrift panel

- EcoFlow River/Delta  
- No-name 200 W panel with MC4  
- MC4→XT60 cable  

**OK if:** Voc in range, polarity correct. Brand of panel irrelevant.

### Example C — failure pattern

- 3s series of 12 V panels → Voc ~66 V  
- Cheap controller max 50 V  
- Result: dead controller  

**Fix:** rewire 2S or parallel, or get higher-Voc MPPT.

### Example D — chemistry mismatch

- AGM battery  
- Controller left on “Li” high voltage  
- Result: dry-out / damage over time  

**Fix:** profile = sealed/AGM per battery sheet.

---

## 8. Communication buses (when brand matters)

Some modern gear talks CAN / RS485 / proprietary:

- Battery BMS ↔ inverter “closed loop”  
- Portable station ↔ official extra battery  
- Smart shunts / monitors  

**Open-loop** still works: inverter and charger use voltage only.  
Survival priority: open-loop voltage systems are more repairable with mixed brands.

---

## 9. Adapters and “universal” cables

- Buy or build adapters only after polarity proof.  
- Label every homemade cable with permanent marker: `PV MC4→XT60 +/− verified`.  
- Avoid stacking five cheap adapters (resistance + failure points).

---

## 10. Mixed-brand field worksheet

Copy for each build:

```
Panel brand/model: ________  Voc: ____  Vmp: ____  Imp: ____  Pmax: ____
Array config:  __S  __P   Array Voc: ____  Array Imp: ____

Controller/PPS brand: ________  Max Voc: ____  Max A: ____  Battery modes: ________

Battery brand: ________  Chemistry: ________  V: ____  Ah: ____  Max charge A: ____

Inverter brand: ________  W cont: ____  Input V: ____

Fuse sizes: Bat-controller ____  Bat-inverter ____  PV string ____

Polarity verified: [ ]   Battery-first connect: [ ]   Notes: ________
```

Continue → [`../05_US_Brands_How_They_Work/README.md`](../05_US_Brands_How_They_Work/README.md)
