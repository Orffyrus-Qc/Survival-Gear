# 01 — Fuel Types: Gasoline, Diesel, Propane & Natural Gas

People say “gas generator” for any fossil unit. Mid knowledge means naming the **fuel** and the **duty** (portable vs standby).

---

## 1. Comparison matrix

| Fuel | Typical machines | Runtime / logistics | Cold climate (Canada) | Notes |
|------|------------------|---------------------|------------------------|--------|
| **Gasoline** | Most portables | Hours per tank; degrades in months | OK if fresh fuel + winter oil; hard after long storage | Easy to buy; worst long-term storage |
| **Diesel** | Larger portables, commercial, some standby | Excellent for long run; high energy density | Excellent once warm; needs correct winter diesel / anti-gel | Efficient under load; louder; heavier |
| **Propane (LP)** | Dual-fuel portables, many home standbys | Long storage if tank full; tank swap/refill | Excellent cold start; slightly less power than gas on some dual-fuel | Rural Canada favourite; no carb varnish |
| **Natural gas (NG)** | Home standby (utility line) | Unlimited as long as gas grid is up | Excellent; no on-site liquid storage | Urban/suburban; ice storm may still leave gas on when electric fails |
| **Tri-fuel** | Some portables | Gas + LP + NG kit | Flexible | Convenience over peak efficiency |

---

## 2. Gasoline (essence)

### How it works

Liquid gas → carburetor or EFI → combustion → engine spins alternator → AC.

### Pros

- Cheapest entry portables  
- Fuel at every station  
- Huge model selection (Honda, Yamaha, Champion, Westinghouse, Generac, etc.)

### Cons

- **Ethanol fuel** ages poorly (gummed carbs after months)  
- Short useful storage without stabilizer (~3–12 months depending on conditions)  
- Spill / vapour fire risk  
- Not ideal as sole multi-week cottage strategy without rotation

### Survival habits

- Stabilize fuel; rotate cans every season  
- Run dry or use valve procedures per manual before storage  
- Prefer **inverter** units for electronics (cleaner power)

---

## 3. Diesel

### How it works

Compression ignition — **no spark plugs** (different from gasoline “ignition”). Glow plugs / intake heaters help cold starts. Governor holds RPM; alternator makes 60 Hz AC (North America).

### Pros

- Fuel efficient under continuous load  
- Diesel stores longer than gasoline (still treat water/algae)  
- Common on farms, job sites, telecom backup  
- High torque for large alternators

### Cons

- Higher purchase price  
- Heavier; more noise/vibration on cheap units  
- **Winter gelling** — need seasonal diesel / additives in Canadian cold  
- Home residential **diesel standby** is less common than NG/propane (emissions, smell, fuel delivery) but excellent for remote/commercial

### When diesel is the right Canadian fit

- Remote site, long outages, you already bulk-store diesel  
- Workshop / farm / telecom hut  
- You want fewer hours of fuel logistics per kWh

---

## 4. Propane (LP — propane / GPL)

### How it works

Pressurized liquid in tank → regulator → gaseous fuel → engine (often dual-fuel with gasoline).

### Pros

- **Stores indefinitely** in a sealed tank (great for preparedness)  
- Cleaner carb behaviour (less varnish)  
- Strong cold-start behaviour  
- Common rural delivery (Canadian propane companies)

### Cons

- Slightly lower max watts on many dual-fuel engines vs gasoline mode  
- Tank freeze / regulator icing if undersized for demand in extreme cold (sizing matters)  
- Outdoor tank placement rules and clearances

### Canadian note

Propane is often the **best liquid fuel for standby and dual-fuel portables** in rural Québec / Prairies / Atlantic when natural gas is unavailable.

---

## 5. Natural gas

### How it works

Utility pipe → meter → generator gas train → engine. No refuelling cans.

### Pros

- “Unlimited” runtime during multi-day outages **if** gas network stays pressurized  
- Ideal for **automatic standby**  
- No gasoline degradation problem

### Cons

- Only where NG service exists  
- Rare regional gas outages / pressure issues  
- Must be installed by qualified gas fitter + electrician  
- Slightly less energy density → unit may be derated vs LP on some models

### Canadian note

Many suburban homes with NG furnaces already have the right utility for a **10–24 kW standby**. Confirm load: electric heat / heat pumps need much larger systems or partial-home critical loads only.

---

## 6. “Gas” vs diesel — decision guide

| Choose **gasoline / dual-fuel portable** if… | Choose **diesel** if… | Choose **propane / NG standby** if… |
|----------------------------------------------|------------------------|--------------------------------------|
| Budget, camping, short outages | Long continuous runtime | Hands-off home auto-start |
| You can rotate fuel | You bulk fuel already | Multi-day ice storm planning |
| Quiet inverter for electronics | Jobsite / farm | You want no weekly gas cans |

---

## 7. Power quality (all fuels)

| Type | Best for |
|------|----------|
| **Conventional open-frame** | Tools, heaters — higher THD, louder |
| **Inverter generator** | Laptops, modern furnace controls, EcoFlow charging |
| **Standby (NG/LP)** | Whole or partial home; designed for ATS |

---

## 8. Fuel math (rough)

```
Runtime hours ≈ (Tank energy × efficiency) / Load kW
```

Rules of thumb (very approximate — check manual):

- Portable 2–3 kW load: often 6–12 h per tank depending on size  
- Standby 10–20 kW on NG: runtime limited by maintenance intervals, not a gas can  
- Dual-fuel: expect **less** max wattage on propane than gasoline mode

---

## 9. Mid-knowledge vocabulary

| Term | Meaning |
|------|---------|
| Dual-fuel | Gasoline + propane (switchable) |
| Tri-fuel | Gas + LP + NG |
| Derate | Lower available watts on LP/NG or altitude/cold |
| Wet stacking | Diesel running too light a load → soot (run under decent load periodically) |
| Transfer switch | Safe way to feed house circuits |
| Bonded neutral | Neutral-ground scheme — must match home/inlet design |

Continue → [`../02_Portable_vs_Standby/README.md`](../02_Portable_vs_Standby/README.md)
