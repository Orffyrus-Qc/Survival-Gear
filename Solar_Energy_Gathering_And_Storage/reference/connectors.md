# Connector Quick Reference

| Connector | Typical use | Notes |
|-----------|-------------|-------|
| **MC4** | Panel strings | Waterproof when seated; use unlock tool |
| **MC4 branch (Y)** | Parallel panels | Fuse strings when paralleling multiples |
| **XT60** | EcoFlow-class solar/car, hobby high current | Polarity keyed; verify adapters |
| **XT90** | Higher current than XT60 | Same family habits |
| **Anderson SB50/SB175** | Winch, DIY DC, some stations | Genderless housing; contact gender matters |
| **Anderson Powerpole** | Ham radio, modular DC | Color standard red=+ |
| **SAE 2-pin** | Battery tenders, some solar maintainers | Easy reverse if cable flipped — meter it |
| **DC5521 barrel** | Accessory ports on some PPS | Check center polarity |
| **Cigarette / car socket** | 12 V accessories | Poor for high continuous A |
| **Ring lug** | Battery studs, inverters | Crimp quality is everything |
| **IEC C13/C14** | AC gear | Not for raw battery DC |

## Adapter rule

Every adapter is a chance to reverse polarity.  
**Multimeter continuity + voltage check before first mating with expensive gear.**

## Homemade cable label template

```
FROM: MC4 panel
TO: XT60 PPS
RED = +
TESTED: 2026-__-__
VOC SEEN: __ V
```
