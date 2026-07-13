# Spec Cheat Sheet

## Voltage quick facts

| System | Nominal | Resting full (approx) | Typical charge absorb (approx — verify!) |
|--------|---------|----------------------|------------------------------------------|
| Lead-acid 12 V | 12 V | ~12.7 V | ~14.4–14.7 V |
| LiFePO4 12 V (4s) | 12.8 V | ~13.3–13.6 V | ~14.2–14.6 V (use BMS/maker) |
| 24 V bank | 24 V | ~25.4 V (LA) | ~28.8 V class |
| 48 V bank | 48 V | ~50.8 V (LA) | ~57.6 V class |

## Panel “12 V” vs true volts

A “12 V panel” is **not** 12 V output in sun. Typical:

| | Approx |
|--|--------|
| Vmp | 17–19 V |
| Voc | 21–23 V |

That headroom is normal for charging a 12 V battery through a controller.

## Rough runtime math

```
Runtime hours ≈ (Battery Wh × usable fraction) / Load W
Battery Wh ≈ Voltage × Ah
```

Examples of usable fraction:

- Lead-acid survival: often plan **50%** DoD for life  
- LFP: often **80–90%** usable if BMS healthy  

Inverter loads: divide by ~0.85–0.9 for conversion loss.

## Controller sizing sketch

```
Charge A ≈ Panel W / Battery V
Pick controller ≥ that × 1.25 margin (site dependent)
```

## Wire current (very rough chassis short runs — verify ampacity tables)

| AWG | Ballpark continuous (short, good copper, free air) |
|-----|-----------------------------------------------------|
| 16 | ~10 A |
| 14 | ~15 A |
| 12 | ~20 A |
| 10 | ~30 A |
| 8 | ~40–50 A |
| 4 | ~70–85 A |
| 2 | ~95–115 A |

*Chassis automotive tables differ from building code. When in doubt, go thicker.*

## Voc cold-temperature warning

Panel Voc **rises** in cold. Series strings designed in summer can exceed controller max in winter morning sun. Leave margin under max Voc.

## EcoFlow / PPS solar mental model

```
Third-party panel OK ⇔ Voc & current within station manual
Official expander only for capacity stacking on that brand line
```

## Connect order (tattoo this)

```
DIY: Battery → Controller → Panels → Loads
PPS solar: Verify polarity → Cover panel → Plug → Uncover
```
