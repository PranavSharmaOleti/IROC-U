# MACH1 — Battery Lifecycle Model

```
SoH(t, EFC) = 1.02 − A_cal·t^α·Arrhenius(T)·k_SOC − k_cyc·DoD^β·Arrhenius(T)·(EFC·8)
```

Everything below is a decomposition of that one line: a fitted offset, then two
degradation terms — calendar first, cycle second — each scaled by its own
`Arrhenius(T)`.

---

**Calibration basis — the cell the model is fitted to, and the defaults it ships with**

- **Cell** · Sony/Murata US26650FTC1 — 3 Ah LFP/graphite cylindrical
- **Basis** · 885 days · 17 test points × 3 cells · <2.2% max error on capacity fade
- **Setup** · α = 0.50 · β = +1.00 · DoD ≈ 57%
- **Source** · Naumann et al. 2018, J. Energy Storage 17, 153–169

---

## Table 1 — Where every term in the equation comes from

Read left to right, in the equation's own order: offset, then calendar term,
then cycle term. Seven factors are fitted or cited and locked; two are contested
in the open literature, and both are what make the next table a range.

| Symbol | Term | Value | Source | Status |
|:--|:--|--:|:--|:--|
| `1.02` | cal · offset | 1.02 | fitted intercept | locked |
| `− A_cal` | cal · coefficient | — | Naumann 2018 | locked |
| `·  t^α` | cal · time exponent | **0.42 → 1.00** | Lewerenz '17 · Naumann '18 · Gasper '21 · Liu '18 | **⚠ CONTESTED — 32 kWh pack** |
| `·  Arrhenius(T)` | cal · temperature | Ea 17.126 kJ/mol (capacity) | Naumann 2018 | locked |
| `·  k_SOC` | cal · SOC factor | 0.6140 @ 66% mean SoC | Naumann 2018 (literal form) | locked |
| `− k_cyc` | cyc · coefficient | — | Naumann 2018 | locked |
| `·  DoD^β` | cyc · DoD exponent | **−0.40 → +1.00** | Gauthier '22 · Eldesoky '22 · Eldesoky '20 | **⚠ CONTESTED — 7 kWh pack** |
| `·  Arrhenius(T)` | cyc · temperature | Ea 71.827 kJ/mol (resistance) — **4.2× the capacity Ea** | Naumann 2018 | locked |
| `·  EFC · 8` | duty · full-charge count | ~200 EFC/yr → 1548 @ yr 8 | duty: 12.84 kWh/100 km · 25.68 kWh/day | locked |

*Slide caption — one equation, nine factors: seven fitted or cited and locked, two still argued over in print.*

**Closing the contested rows — the validation programme that resolves them, not splits them**

- **Test** · 6 cells · 40–45 °C · 90–100% SoC · ≥18 months

> **Caption text — Table 1**
>
> The two contested rows are the entire uncertainty budget. On **α**, Lewerenz '17 measured
> linear fade across 50 LFP cells and got 1.00, while Naumann '18 fitted √t and got 0.50, with
> Gasper '21 at ~0.45 and Liu '18 at 0.42 — a **2.3× spread that swings the pack from 44 to
> 76 kWh**. On **β**, Gauthier '22 reports +1.0 at 40 °C, Eldesoky '22 finds no DoD dependence
> at all below a 4.06 V cut-off, and Eldesoky '20 reports −0.40 at 55 °C, which swings the pack
> by 7 kWh. So the bands in Table 2 are not vagueness in our model — every band traces to
> exactly one unresolved literature disagreement, and α is the dominant one; the validation
> programme above is built to close both rather than split the difference.

---

## Table 2 — What the equation predicts

Pack size required to meet fleet duty, and degradation at year 8, by cell temperature

| Cell temp | Pack required (band) | Pack @ defaults | SoH @ yr 8 (band) | SoH @ defaults | R_inc @ yr 8 | Verdict |
|:--|--:|--:|--:|--:|--:|:--|
| 26 °C | 37.1–53.3 kWh | 37.2 kWh | 59.5–85.5% | 85.2% | +14.0% | ✓ Wide margin |
| **40 °C** | 40.6–74.6 kWh | 41.0 kWh | 42.5–78.1% | 77.3% | +50.9% | ✓ Achievable |
| **48 °C** ★ | 43.3–100.1 kWh | 44.2 kWh | 31.7–73.2% | 71.8% | +101.3% | ⚠ Band too wide |
| 55 °C | 46.2–**140+** kWh | 47.8 kWh | 22.0–68.6% | 66.4% | +179.8% | ✗ Infeasible |

★ 48 °C is our design point (liquid-plate cooling). At default parameters our **45 kWh** pack
meets duty, with 193 EFC/yr and 1548 EFC by year 8.

**The ✗ at 55 °C refers to the band's worst corner** (β = −0.40 with α = 1.00), not to our
defaults — the default there still closes at **47.8 kWh**. Every temperature in this table has
a finite default answer; what runs away with heat is the *width* of the band. At 55 °C the worst
corner passes the model's 140 kWh search ceiling — roughly 3× our 45 kWh sedan — and we did not
raise that ceiling to manufacture a finite answer.

*Slide caption — our default closes at every temperature; it is the width of the band, not the answer, that runs away with heat.*

> **Caption text — Table 2**
>
> Every band here is Table 1's two contested parameters carried forward — α contributes 32 kWh
> and β contributes 7 kWh — so the width is the literature disagreement, not vagueness in our
> model; the defaults are finite and specific at every temperature, which is the whole reason we
> default rather than average. What degrades with temperature is the worst corner of the band,
> and at 55 °C that corner passes the model's 140 kWh search ceiling, roughly 3× our 45 kWh
> sedan. We did not raise the ceiling to manufacture a finite answer, because a corner where the
> disagreement stops being resolvable is precisely the thing we are designing away from. That is
> why the vehicle is specified to a 48 °C cell on liquid-plate cooling: far enough from that
> corner that the disagreement still resolves into a pack we can actually build.

---

**Warranty claim boundary — two separate claims, kept separate on purpose**

Time-to-80% at 40 °C differs **3.6×** between Naumann (13.3 yr) and Lewerenz (3.7 yr), so
**8-year / 80% is not a defensible claim** on this evidence. First life (~15 yr at our duty) is
solid; it is the **warranty** that is the uncertain claim. We size and cool the pack against
first-life physics, and we do not sell an 8-year warranty the literature will not carry.