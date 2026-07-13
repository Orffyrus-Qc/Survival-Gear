# Generators — Gas, Diesel & Auto-Start for Outages

**Level:** key hands-on → mid knowledge  
**Focus:** fuel types, portable vs home standby, automatic start / transfer systems, **best fit for Canada** (including Québec cold-climate and service reality)  
**Pairs with:** [`../Solar_Energy_Gathering_And_Storage/`](../Solar_Energy_Gathering_And_Storage/) — solar reduces fuel burn; generators cover multi-day winter outages and high surge loads.

**Version française :** [`../fr/Generators_Gas_Diesel_Auto_Start/README.md`](../fr/Generators_Gas_Diesel_Auto_Start/README.md)

## What you will be able to do

1. Choose **gasoline, diesel, propane (LP), or natural gas** for your use case.  
2. Tell **portable** gear from **home standby** and size watts for fridge, well pump, furnace blower, sump.  
3. Explain **auto-ignition / auto-start** and **ATS (Automatic Transfer Switch)** when the grid dies.  
4. Pick brands and install paths that fit **Canadian** code, fuel, cold weather, and dealer support.  
5. Combine generator + solar/battery without backfeeding the grid (illegal and deadly).

## Study order

| # | Folder | Topic |
|---|--------|--------|
| 01 | [`01_Fuel_Types_Gas_Diesel/`](./01_Fuel_Types_Gas_Diesel/) | Gas, diesel, propane, natural gas — pros/cons |
| 02 | [`02_Portable_vs_Standby/`](./02_Portable_vs_Standby/) | Classes of machines, sizing, connectors |
| 03 | [`03_Auto_Start_ATS_Outage/`](./03_Auto_Start_ATS_Outage/) | Sensors, ATS, interlocks, weekly exercise |
| 04 | [`04_Canadian_Brands_Best_Fit/`](./04_Canadian_Brands_Best_Fit/) | Canada/Québec service, CSA, brand matrix |
| 05 | [`05_Cold_Climate_Safe_Ops/`](./05_Cold_Climate_Safe_Ops/) | Winter start, CO, fuel storage, ice storms |
| 06 | [`06_Hybrid_With_Solar/`](./06_Hybrid_With_Solar/) | Generator + EcoFlow / DIY solar without conflict |
| — | [`LEARNING_PATH.md`](./LEARNING_PATH.md) | Checklist |
| — | [`reference/`](./reference/) | Cheat sheets |

## Core energy path (generator)

```
FUEL (gas / diesel / propane / NG)
   ↓
ENGINE  →  ALTERNATOR  →  AC power (120/240 V)
   ↓
Manual cord / inlet  OR  Automatic Transfer Switch (ATS)
   ↓
SELECTED HOME CIRCUITS  (or whole panel if sized for it)
```

**Auto-start path (standby):**

```
Utility power fails
   → ATS or controller senses loss
   → Engine cranks (auto ignition / electric start)
   → Generator builds voltage / frequency
   → ATS transfers loads to generator
   → Utility returns → cool-down → transfer back → engine off
```

## Safety baseline (this module)

- **Carbon monoxide kills** — never run a portable indoors, in a garage (even “open”), or near air intakes.  
- **Backfeeding** a dryer outlet into the panel without a proper interlock/ATS can **kill line workers** and burn your house.  
- Fuel is fire risk: storage limits, venting, separation from living space.  
- Permanent standby + ATS = **licensed electrician** (and often gas fitter for NG/propane). In Québec: respect **RBQ** / electrical permit rules.  
- This is educational — not a substitute for CSA/CEC installs or manufacturer manuals.

## Quick start

1. Read fuel types (01) so “gas vs diesel” is not a brand argument.  
2. Decide portable (budget / cottage) vs standby (home auto-outage) in 02.  
3. Study ATS auto-start (03) before shopping “whole house.”  
4. Use the **Canadian best-fit** matrix (04) for dealers and climate.  
5. Wire your mental model to solar in 06.

Next → [`01_Fuel_Types_Gas_Diesel/README.md`](./01_Fuel_Types_Gas_Diesel/README.md)
