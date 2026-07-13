# 06 — Hybrid: Generator + Solar / Battery

Generators and solar solve different failure modes. Together they cut fuel use and cover multi-day Canadian winters.

---

## 1. Layered power (recommended mental model)

| Layer | Duration | Tool |
|-------|----------|------|
| 0–seconds | Seamless for some devices | UPS / PPS pass-through |
| Minutes–hours | Silent | Battery (EcoFlow-class or DIY bank) |
| Daytime recovery | Renewable | Solar panels |
| Multi-day / surge / deep winter | Fuel | Generator |
| Unattended home | Auto | Standby + ATS |

---

## 2. Safe ways to combine

### A. Generator charges portable power station

```
Inverter generator → AC wall charger on EcoFlow/Bluetti/etc. → DC loads + later AC from station
```

- Prefer **inverter** generator (cleaner AC, efficient at partial load)  
- Charge station, then shut gen to save fuel  
- Avoid running gen 24/7 for small USB loads  

### B. Generator charges DIY battery via charger / inverter-charger

```
Generator → AC charger or Victron-class inverter-charger → battery bank → inverter → loads
```

- Settings must match battery chemistry  
- Fusing and cable size as in solar module  

### C. Standby ATS house + separate solar station

```
Standby handles hardwired critical circuits
Solar/PPS handles phones, lights, office island — optional
```

Do **not** backfeed solar inverter output into a generator bus unless the inverter is **explicitly** listed for generator input / hybrid interaction.

### D. Hybrid inverters with generator input

Some off-grid/hybrid AIOs accept generator as AC input to charge batteries. Follow that brand’s generator size and grounding rules.

---

## 3. Unsafe / illegal patterns

| Pattern | Why bad |
|---------|---------|
| Two sources on one outlet without transfer | Backfeed / fight / fire |
| Solar microinverters + portable gen on same random circuit | Complex protection issues |
| DIY “suicide cord” | Line worker hazard |
| Gen and utility both tied without interlock | Same |

---

## 4. Fuel-saving strategy

1. Solar + battery carry quiet loads.  
2. Start generator when battery SoC hits a floor (e.g. 20–40%) **or** when a high surge load is needed.  
3. Run gen under **decent load** (charge hard + run heat/pump) rather than idling for a phone.  
4. Shut down when SoC high again.  
5. Weekly standby exercise still applies even if solar exists.

---

## 5. Sizing hybrid for a Canadian outage week

Example planning sketch (not a design stamp):

| Item | Role |
|------|------|
| 2–5 kWh battery / PPS | Nights + quiet |
| 400–2000 W solar | Day refill when sun exists |
| 2–7 kW inverter portable **or** 10–22 kW standby | Storm, well, long cloud |

Cloudy ice-storm weeks → **fuel plan dominates**; solar is bonus.

---

## 6. Link back to solar module

- Component ID, polarity, fusing: `Solar_Energy_Gathering_And_Storage`  
- EcoFlow charge from gen = AC input, not solar XT60  
- Scrap solar tote can keep lights while gen runs the well pump  

---

Back to module home → [`../README.md`](../README.md)
