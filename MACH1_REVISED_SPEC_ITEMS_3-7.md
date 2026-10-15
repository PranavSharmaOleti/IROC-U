# MACH1 / FleetLine E1 — Revised Battery & Powertrain Specification

*Items 2–7 of the review plan. LFP focus. Every figure traceable to a source or to the model at `/tmp/opencode/mach1/mach1_model.py`.*

---

## ⚠ CORRECTIONS AFTER SELF-AUDIT (`self_audit.py`)

Fourteen items below were overstated or wrong on first pass. Use these.

C1–C4 are the original self-audit pass and are retained **unaltered** for traceability. **C5–C7 supersede C1 and C2** where they overlap — they widen a single number into a band on newly incorporated peer-reviewed evidence. **C8–C14 supersede C5 and C6**: five further papers (Naumann 2018, Lewerenz 2017, Eldesoky 2020, Waldmann 2014, Pozzato 2023) changed the *default calibration* and the results moved again, adversely. Where any earlier correction disagrees with a later one, the **latest** governs.

Model sections **[1]–[11] retain the legacy "Yagci" calibration and are unchanged**, so every number in C1–C7 still reproduces exactly. Sections **[12]+ carry the new Naumann 2018 default.**

### C1 — Pack size: 44 kWh, not 40 kWh

The 40 kWh figure relied on a scenario assuming **cell temperature 5 °C *below* ambient** (40 °C cell at 45 °C ambient). That requires an active chiller loop, not a standard cold plate. Typical liquid-cooled packs run cell temperature at or slightly above ambient. The realistic case is +3 °C (48 °C cell), which needs **44.0 kWh** at base consumption.

40 kWh is valid **only if a 40 °C cell temperature is demonstrated**, not assumed.

### C2 — The 80% year-8 threshold is NOT robust to the superposition method at 48 °C cell

| Cell °C | Linear superposition | RSS | Delta |
|---|---|---|---|
| 55 | 62.3% | 72.5% | +10.2 pp |
| **48** | **72.5%** | **80.1%** | **+7.5 pp** |
| 40 | 81.4% | 86.7% | +5.3 pp |
| 26 | 91.5% | 94.2% | +2.7 pp |

**At 48 °C the answer straddles 80% depending on method.** Linear says fail, RSS says pass. At 40 °C both clear it comfortably. The cooling spec therefore decides not just pack size but whether an 80% warranty claim survives — which is a stronger reason to specify 40 °C than the size saving.

### C3 — "HVAC overstated 2.24×" was the wrong framing

The correct statement: **the deck's total daily energy (38.28 kWh) is ~49% above a verified real-world measurement of the same quantity (25.68 kWh, Autocar India AC-on).**

The deck's HVAC line itself (1.20 kW × 8 h) is plausible and arguably conservative against ADAC's measured 1.3–1.5 kW. The error is in the **sum**, not in any single line item. Comparing 14.80 kWh/day (a decomposed budget) against 6.62 kWh/day (an AC-on-minus-derived-AC-off delta, where the AC-off figure is itself derived and the AC-on figure bundles traffic, auxiliaries and regen) is not like-for-like.

### C4 — CRITICAL: "duty met" and "80% SoH at year 8" are different pack sizes

The sizing model guarantees the **shift is completed** at end of life. It does **not** guarantee an 80% state-of-health. Solving each separately:

| Cell temp | Meets duty (10% EOL reserve) | Meets **80% SoH @ 8 yr** | Gap |
|---|---|---|---|
| 55 °C | 49.2 kWh | **120.0 kWh** | +70.8 kWh |
| **48 °C** | 44.0 kWh | **90.4 kWh** | **+46.4 kWh** |
| **40 °C** | 39.9 kWh | **41.1 kWh** | **+1.2 kWh** |
| 26 °C | 35.5 kWh | (below 35 kWh) | converged |

Under RSS superposition the 48 °C case still needs ~81–89 kWh.

**Consequence: at 48 °C cell temperature, an 80% year-8 warranty is not achievable in a 45 kWh-class compact sedan at all.** 90 kWh is roughly 300 L and ~640 kg of pack — outside both the floor pan and the mass budget.

**At 40 °C cell temperature the two requirements converge to within 1.2 kWh.**

This makes the ≤40 °C cell-temperature specification a **hard requirement, not an optimisation** — not because it saves 4 kWh, but because it is the difference between a 44 kWh vehicle and a 90 kWh one that cannot be built.

### C5 — Pack size is a RANGE, not 44.0 kWh (superseded by C8–C14)

C1's 44.0 kWh was the output of one corner of a model that had two hard-coded assumptions: **linear DoD scaling** and a **√t calendar law**. Both are now parameterised on peer-reviewed evidence (Item 8), and both move the answer in the same direction — more pack, not less.

At the realistic **48 °C cell, base consumption, 10% EOL reserve**:

| DoD exponent | cal exponent 0.40 | cal exponent 0.45 | cal exponent 0.50 |
|---|---|---|---|
| **1.00** (old linear assumption) | 42.3 kWh | 43.1 kWh | **44.0 kWh** ← C1's figure |
| **0.50** (sub-linear) | 43.8 kWh | 44.6 kWh | 45.6 kWh |
| **0.00** (flat — Schreiber-consistent) | 45.9 kWh | 46.8 kWh | **47.9 kWh** ← conservative |

**Range: 42.3 – 47.9 kWh. The conservative end is 47.9 kWh.**

Note where C1's 44.0 kWh sits: it is **optimistic on the DoD axis** (linear scaling is exactly what Schreiber refutes) and **conservative on the calendar axis** (√t is the upper bound of Gasper's range). It was a lucky corner, not a central estimate. Do not quote it alone.

At the **40 °C cell** the same sweep gives **38.9 – 42.1 kWh, conservative end 42.1 kWh**.

### C6 — Year-8 SoH is a BAND, not a point estimate (superseded by C8–C14)

The superposition axis already existed (C2). It is now joined by the calendar-exponent axis and the DoD-exponent axis. Pack is always solved on **linear** superposition; the RSS rows re-evaluate SoH at that same pack.

**48 °C cell** — pack 42.3–47.9 kWh:

| Superposition | SoH @ 8 yr across DoD exp × cal exp | Clears 80% |
|---|---|---|
| Linear | **66.2 – 74.9%** | 0 of 9 |
| RSS | **76.6 – 82.6%** | 3 of 9 |
| **Full band** | **66.2 – 82.6%** | **3 of 18** |

**40 °C cell** — pack 38.9–42.1 kWh:

| Superposition | SoH @ 8 yr across DoD exp × cal exp | Clears 80% |
|---|---|---|
| Linear | **75.3 – 81.6%** | 2 of 9 |
| RSS | **83.1 – 87.5%** | 9 of 9 |
| **Full band** | **75.3 – 87.5%** | **11 of 18** |

**This sharpens C2 rather than reversing it.** C2 said the 80% threshold "straddles 80% depending on method" at 48 °C. That remains true — but the straddling band is now 16 pp wide, not 8 pp, and **only 3 of 18 defensible parameter combinations at 48 °C produce an 80% year-8 SoH at all.** At 40 °C the majority (11 of 18) clear it, which is the strongest quantitative argument in this document for the ≤40 °C specification.

### C7 — The 8-year EOL claim carries a 40–50% structural band (Graner 2026)

Every pack and SoH figure above is a *model* output. It is **not** the same thing as an 8-year life claim, and that claim now carries its own, much larger, uncertainty band. See Item 8.3.

---

## ⚠ CORRECTIONS AFTER THE 2nd REWORK — five further papers

**The default calibration changed. The numbers moved. All of them got worse.**

### C8 — The default calendar calibration is now Naumann 2018, and it is WORSE than Yagci

The prior model anchored calendar fade on Yagci et al. (5.11 %/√yr at 35 °C/100% SOC, Ea 37.3 kJ/mol, flat SOC factor 0.75). That anchor is now **legacy**. The default is Naumann et al., J. Energy Storage 17, 153–169 (2018) — a purpose-built LFP calendar fit on a Sony/Murata US26650FTC1 3 Ah cell, 885 days, 17 test points × 3 cells, model error <2.2% on Q_loss.

| | Legacy Yagci | **New default: Naumann 2018** |
|---|---|---|
| Ea | 37.3 kJ/mol (mixed protocols, incl. cathode) | **17.126 kJ/mol** (LFP calendar Q_loss only) |
| SOC factor at 66% mean SOC | 0.75 (flat, assumed) | **0.6140** (fitted cubic, Naumann Eq. 3+6 literal) |
| A_cal at 35 °C, 66% SOC | 3.8325 %/√yr | **5.4235 %/√yr** |
| 8-yr fade at 48 °C cell | 10.1% | **20.1%** |

**The lower activation energy is misleading.** Naumann's Ea is small, so the *temperature derate* is mild — but the SOC-normalised anchor is 1.48× larger, and the anchor wins by a wide margin. **Net effect at 48 °C cell: the 8-year calendar fade roughly doubles.**

### C9 — Resistance growth is a separate warranty exposure the pack-size claim does not cover

Naumann's R_inc activation energy is **71.827 kJ/mol — 4.2× the capacity-loss activation energy** — and R_inc is fitted **linear in t**, not √t.

| Cell temp | R_inc rate | **R_inc @ 8 yr** | Q_loss fade @ 8 yr |
|---|---|---|---|
| 55 °C | 22.48 %/yr | **+179.8%** | 22.1% |
| 48 °C | 12.66 %/yr | **+101.3%** | 20.1% |
| 40 °C | 6.37 %/yr | **+50.9%** | 17.1% |
| 26 °C | 1.75 %/yr | +14.0% | 12.6% |

**At 48 °C cell, peak power falls to ~50% of new by year 8.** An 8-year/80%-capacity warranty says nothing about this. **Peak power and DC charge acceptance must be warranted separately from capacity, or the warranty is incomplete.**

**A second Naumann finding worth stating:** because their R_inc SOC term is a *downward* parabola peaking at 50% SOC, our 66% mean SOC ages in resistance **faster in resistance than 100% SOC** (1.4736 vs 0.7128). Storing less full is worse for power, not better. *(An earlier draft put this at 2.07×; that figure came from the erroneous renormalised form — see C15.)*

**Unreconciled conflict:** Lewerenz 2017 reports internal resistance is "hardly influenced" up to 40 °C. Naumann fits 71.827 kJ/mol. Both are LFP. They cannot both be right, and Lewerenz publishes no numeric rate, so it cannot be settled from the papers in hand. The Naumann figures are the pessimistic side of an open gap.

### C10 — The calendar time exponent is CONTESTED across LFP studies: 0.45 to 1.00

| Study | Chemistry | Method | Exponent | Status |
|---|---|---|---|---|
| Gasper 2021 | NMC + LFP pooled, 17 datasets | inference | ~0.45 | not LFP-specific. **CITATION INCOMPLETE — unverified, and its article number is wrong (C16).** Not load-bearing: the sweep spans 0.45–1.00 and the conservative bound comes from Lewerenz. If it cannot be completed, delete this row. |
| Naumann 2018 | **LFP** | fit, √t | **0.50** | default |
| **Lewerenz 2017** | **LFP** | **direct measurement, linear** | **1.00** | **conservative bound** |

**0.50 must not be presented as central.** Lewerenz measured linear fade on LFP at 25–40 °C — at exactly our operating temperature. That is a measurement, not an inference, so **exponent 1.00 is the conservative bound.**

**Under a "hold year-1 fixed" normalising convention** (fade(t) = A·t^p with A = the year-1 fade), Naumann and Lewerenz are directly comparable:

| Cell temp | Calibration | Year-1 rate | 8-yr fade @ p=0.5 | 8-yr fade @ p=1.0 |
|---|---|---|---|---|
| 40 °C | Naumann | 6.03 %/yr | 17.1% | 48.3% |
| 40 °C | **Lewerenz** | **5.83 %/yr** | 16.5% | **46.7%** |
| 48 °C | Naumann | 7.11 %/yr | 20.1% | 56.9% |
| 48 °C | **Lewerenz** | **6.87 %/yr** | 19.4% | **55.0%** |

**Lewerenz is SLOWER in year 1 but far worse by year 8. Long-horizon behaviour is governed by the exponent, not the year-1 rate** — which is why the validation programme (Item 8.5) must run to 80% SoH and must not stop at 12 months. **A 12-month test cannot discriminate between these two.**

**Open gap:** Lewerenz reports **no fitted activation energy**. Scaling it away from 40 °C borrows Naumann's 17.126 kJ/mol, so every Lewerenz number outside 40 °C is a two-source extrapolation, not a Lewerenz measurement.

### C11 — CRITICAL: under Lewerenz, the 8-year/80% warranty is NOT REACHABLE at 40 °C cell

This is not a sizing band. It is a risk to the warranty structure itself.

| Cell temp | Naumann p=0.5 | **Lewerenz p=1.0** | legacy Yagci p=0.5 |
|---|---|---|---|
| 40 °C | 13.3 yr | **3.8 yr** | 20.7 yr |
| 48 °C | 9.6 yr | **3.2 yr** | 10.1 yr |

*(Years for calendar fade alone to take SoH from 1.02 to 0.80. Cycling is ignored, so these are upper bounds — a real pack reaches 80% **earlier**, never later.)*

Our independent recomputation of Lewerenz's Table 6 slopes (1.6333 %/100 d at 40 °C/50% SOC → 5.96 %/yr → 22 pp fade in 3.69 yr) **reproduces Lewerenz's own stated conclusion: "over 3–4 years storing at 40 °C"** — against "over 20 years storing at 25 °C".

**Consequence:** the ≤40 °C cell specification, previously argued on pack size and on the 80% SoH threshold, now also carries the warranty. **A 45 kWh-class sedan in this duty cannot carry an 8-year/80% warranty at 40 °C cell under the Lewerenz exponent.** Either the cell must run cooler, the duty must change, or the warranty term must change. Those are product decisions, not modelling ones.

### C12 — The DoD exponent sweeps NEGATIVE, and no single exponent is defensible

The DoD exponent now spans **−0.40 to +1.00** and, critically, **changes sign with temperature**:

| Cell temp | DoD exponent | Source | Chemistry |
|---|---|---|---|
| 20 °C | ~0.00 | Schreiber 2025 + Gauthier 2022 | NMC / NMC622 |
| 40 °C | **+1.00** | Gauthier 2022 ("increases with DOD", linear) | NMC622 |
| 48 °C | **+0.25** | ***ASSUMPTION — NO MEASUREMENT EXISTS*** | — |
| 55 °C | **−0.40** | Eldesoky 2020 (ratio 1.32 → −0.4005) | **LFP** |

The curve is **non-monotonic**: it rises from ~0 at 20 °C to +1.00 at 40 °C, then falls through zero near **50.7 °C** to −0.40 at 55 °C. Eldesoky's −20 °C result (*"only the cells aged with 100% DOD exhibit a distinct difference"*) independently supports a sign inversion at low temperature.

**The 48 °C anchor is the model's weakest point.** It is the only point on the curve with no measurement behind it — and it is the point we operate at. The curve also mixes chemistries (NMC, NMC622, LFP, assumed) and is an **interpolation through four points, not a fit**.

**The one genuinely encouraging result:** because the exponent passes through ≈0 at our operating point, **pack-size sensitivity to DoD scaling is LOWEST exactly where we operate**, and largest at the 40 °C and 55 °C ends. See Item 8.4.

### C13 — 25 °C cell is now a hard modelling floor (Waldmann 2014)

Waldmann et al., J. Power Sources 262, 129–135 (2014) found **two Arrhenius mechanisms with opposite temperature sign** (both R² = 0.99, proven by post-mortem plus reference electrodes):

- **Above 25 °C:** Ea = **+0.38 ± 0.02 eV** (36.66 kJ/mol) — SEI growth + cathode degradation
- **Below 25 °C:** Ea = **−0.57 ± 0.02 eV** — Li plating, an exothermic adsorption/desorption equilibrium on plated lithium, and a **charging** effect

**Do not extrapolate this model below 25 °C cell temperature.** `solve_min_pack()` now raises on any cell temperature below 25 °C. **The immersion scenario sits at 26 °C — 1 °C above a mechanism change.** Every immersion figure in this document is indicative only, not a design point.

**And do not read these two numbers as contradictory:**

- **Waldmann 36.66 kJ/mol** = CYCLE ageing at 1C, **NMC/LMO blend cathode, including cathode degradation**
- **Naumann 17.126 kJ/mol** = CALENDAR ageing, **LFP/graphite, capacity loss only**

Different quantities, different chemistries, different ageing modes. The 36.7 vs 37.3 kJ/mol near-match is coincidental.

### C14 — Citation corrections (two of them were wrong)

1. **The file named `louli_dahn_2019_LFP_DoD.txt` is not Louli & Dahn.** It is **Gauthier et al. 2022**, JES 169, 020518, DOI 10.1149/1945-7111/ac4b82 — NMC622/natural graphite, VC211 pouch cells, 7 SOC ranges, 20 °C and 40 °C. It is cited correctly throughout this revision. **Louli & Dahn 2019, JES 166 A3031 remains OUTSTANDING — it is not in hand and is listed as a gap, never cited as held.**
2. **Gasper 2021's citation could NOT be verified and its article number is wrong.** Both candidate DOIs 404 at Crossref and doi.org, and JES 168/020502 is a different paper. **See C16 for the full check.** It must be completed, or the citation deleted, before external submission.
3. **The "5th paper" filename in the brief was wrong.** The file supplied as a simplified calendar model is Liu et al., *Solid State Ionics* 320 (2018) 126–131 — 18650 cells, not Lewerenz, not 8 Ah. The real Lewerenz 2017 paper is present under a different name and is the actual source for the linear-calendar findings.

### C15 — Naumann SOC normalisation RESOLVED: the literal convention is correct, and my renormalised form was wrong

I claimed in the first round that the two normalisation conventions were "algebraically identical". **They are not.** Checked against the primary source:

> *"The factors representing the SOC influence kSOC;Qloss(SOC) and kSOC;Rinc(SOC) **CAN BE SET TO A VALUE OF 1** because kref is defined with SOCref = 100%."*

and Eq. (6) `kref;Qloss = Qloss(Tref=25°C, SOCref=100%, tend) / ( kSOC;Qloss(SOCref=100%)·√tend )` — i.e. **`kSOC(100%)` is divided out of `kref`, so it stays in the numerator of the forward model Eq. (3).** The correct evaluation multiplies by `kSOC(SOC) = 0.613954` at 66% SOC. The default is now `NAUMANN_SOC_CONVENTION = "literal"`. The renormalised form is retained **only** so the earlier error stays reproducible; it is not what Naumann's equations say.

| | LITERAL (correct) | renormalised (my error) | error size |
|---|---|---|---|
| Q_loss factor at 66% SOC | **0.613954** | 0.639911 | **+4.06%** |
| R_inc factor at 66% SOC | **1.473608** | 2.067280 | **+28.72%** |
| 8-yr fade at 48 °C cell | **20.1%** | 21.0% | +0.9 pp |
| R_inc @ 8 yr at 48 °C cell | **+101.3%** | +142.1% | **+40.8 pp** |

**And a correction to my own first-round report: I wrote that "the same 4.06% applies to R_inc". That was wrong.** The R_inc factor is `kSOC;R(100%) = 0.712825`, not 0.959437, so the R_inc error was **28.7%, not 4%**. The headline warranty exposure I reported — "+142% resistance growth, peak power ~41% of new" — was inflated. **The correct figure is +101.3% and peak power ~50% of new.** Still a serious exposure, materially less dramatic than I said.

The R_inc error also created a **false finding**: the renormalised form made 66% mean SOC look 2.07× worse than 100% SOC for resistance. Under the literal form the quadratic still favours 100% SOC (1.4736 at 66% vs 0.7128 at 100%), so the *direction* survives, but the magnitude was mine, not Naumann's.

### C16 — The Gasper 2021 citation could NOT be verified, and the article number is demonstrably wrong

Attempted against Crossref, doi.org, and OpenAlex:

| Check | Result |
|---|---|
| `10.1149/1945-7111/abd7a8` (our original) | **404** at Crossref *and* at doi.org |
| `10.1149/1945-7111/abeb5f` (suggested alternative) | **404** at Crossref *and* at doi.org |
| Crossref title search, all works | no match |
| Crossref title search, JES (ISSN 1945-7111) | no match |
| OpenAlex title + full-text search | no match |
| **JES vol. 168, article 020502 (Feb 2021)** | **is a different paper:** *"Challenging Practices of Algebraic Battery Life Models through Statistical Validation and Model Identification via Machine-Learning"*, DOI 10.1149/1945-7111/abdde1 |

**This is worse than "unverified".** The volume and article number in our citation resolve to a different paper. Both candidate DOIs fail to resolve at two independent registries.

**The Gasper 2021 citation in this document is INCOMPLETE and MUST BE COMPLETED before the document is submitted anywhere external.** The underlying claim — that only 1 of 17 calendar-aging datasets contains a 0.5 exponent within its 95% CI, with a pooled exponent ~0.45 — is unchanged and is used only as a *screening* input to the calendar exponent sweep. It is **not load-bearing**: the sweep spans 0.45–1.00 and the conservative bound comes from Lewerenz's direct measurement, not from Gasper. **If the Gasper citation cannot be completed, delete it and the sweep still stands.** I am not guessing a replacement DOI.

---

## Item 2 — Pack architecture: semi-structural CTP, chemistry-agnostic envelope

### Architecture taxonomy and what each locks in

| Generation | Architecture | Structural role | Chemistry flexibility | Examples |
|---|---|---|---|---|
| Gen 0 | **Module-to-Pack** | Non-structural | **Highest** — module is the standardised interface | Hyundai E-GMP, VW MEB |
| Gen I | **Cell-to-Pack (CTP)** | Semi-structural, **detachable** | **Medium** — cell format fixed, chemistry can vary if voltage compatible | CATL Qilin, Renault 5 |
| Gen II | **Cell-to-Chassis (CTC)** | Fully structural — cells are the floor | **Lowest** — format, mechanics and body co-optimised | Tesla 4680, BYD CTB, Leapmotor |

The deck specifies a **structural** pack — Gen II, the *least* reversible option, while claiming maximum reversibility.

### What actually locks chemistry in

| Factor | Blocks swap? | Technical reality |
|---|---|---|
| **Cell physical format** | **Hard lock** | Enclosure, stacking, cooling plate geometry, busbar routing and compression fixtures are all format-specific |
| **Series count / nominal voltage** | **Hard lock** | LFP ~3.2 V, NMC ~3.7 V, Na-ion ~3.0–3.2 V. Series count, AFE channels, contactors, charger window and inverter DC link all change |
| **Thermal propagation safety case** | **Homologation lock** | AIS-038 test parameters are cell-geometry specific — Annex IX-K sets inter-cell gap by cell type. Must be re-validated per chemistry |
| **Crash load paths** | Hard **if** CTC | Cells become cross-car beams; casing modulus and swelling force become crash inputs. LFP works in BYD Blade *because* it swells less |
| **Busbar / interconnect** | Partial | Chemistry-sensitive (thermal expansion, weld geometry) — but common if cell format and terminal position match |
| **Cold plate** | Partial | Depends on cell heat flux. Chemistry-independent if format and max heat flux matched |
| **BMS calibration** | **Firmware lock only** | OCV-SOC curves, balancing and thermal limits are chemistry-specific — but this is a **software** change, not hardware |

### Precedent

**Only VW PowerCo's Unified Cell demonstrates same-envelope multi-chemistry at production intent** — one prismatic can (~256 × 106 × 32 mm class) across LFP, NMC and sodium-ion, same busbar, same cold plate; only series count and BMS parameters change. CATL Qilin *claims* multi-chemistry support but its sodium-ion version is not in the same pack. BYD Blade is format-locked to LFP/LMFP by design.

### The homologation fact that governs this

**AIS-038 Rev.2 Clause 2.48 defines a REESS "type" by chemistry, capacity and physical cell dimensions.** Any cell chemistry change = **new REESS type = full AIS-038 Part II re-test**, including IS 16893 cell certification, thermal propagation, mechanical, IP, BMS protection verification, EMC, vehicle type approval and CoP surveillance.

So chemistry flexibility is not free — it is a *pack architecture* decision that determines whether a future swap costs 4–6 months or 18–24 months.

### Specification

> **Semi-structural CTP with a standardised large-format prismatic cell envelope (~256 × 106 × 32 mm class), qualified for both LFP and sodium-ion. Not cell-to-chassis.**

- **Cell format**: large prismatic, top-terminal — matches CATL Qilin/Shenxing/Naxtra, Gotion, CALB, SVOLT roadmaps
- **Series configuration**: design for **102s–108s** (covers LFP 3.2 V and Na-ion 3.0–3.2 V at 320–350 V). BMS AFE rated to 108s
- **Thermal**: bottom + side cold plate, sized for **≤2.5 kW/cell** heat flux (covers LFP 1–2C and Na-ion 2–3C)
- **Propagation barrier**: aerogel/mica inter-cell + directional venting, validated per Annex X for LFP
- **Structure**: pack housing functionally integrated with the floor panel but **detachable** — bolts to the body, serviceable, replaceable
- **BMS**: common hardware, per-chemistry firmware parameter sets

### Quantified trade-off vs the deck's structural pack

| Metric | Semi-structural CTP | Structural CTC (deck) | Delta |
|---|---|---|---|
| Pack gravimetric (LFP) | 155–160 Wh/kg | 170–180 Wh/kg | −10–15 Wh/kg |
| Pack volumetric (LFP) | 300–320 Wh/L | 350–380 Wh/L | −30–50 Wh/L |
| Pack cost (45 kWh, 2034) | ₹3.8–4.2 L | ₹3.5–3.8 L | **+₹0.3–0.5 L / pack** |
| **Chemistry swap effort** | **4–6 months** | **18–24 months** | 4× faster |
| **Chemistry swap cost** | **₹2–3 Cr** | **₹15–25 Cr** | 8× cheaper |
| Homologation on swap | REESS re-cert + vehicle extension | Full vehicle re-homologation | 6–9 mo vs 18+ mo |
| Production line | Single line, cell swap | Dedicated line per chemistry | — |

**+3–5% pack cost buys an 8× cheaper chemistry option.** For a programme whose entire strategic premise is preserving a future chemistry swap, that is the right trade.

### Why CTP and not module-to-pack

Module-to-pack at 45 kWh LFP would need ~300 L of pack volume — it does not fit a compact sedan floor pan. CTP at ~150–200 L fits. **CTP is the minimum viable architecture here**, and it is also the most chemistry-flexible one that physically fits.

---

## Item 3 — Pack sizing: a range, conditional on thermal spec

### The governing result

**Default calibration: Naumann 2018** (C8). **Calendar time exponent swept 0.45–1.00** (C10). **DoD exponent swept −0.40 to +1.00** (C12).

| Thermal design | Cell °C | **Required pack range** (Naumann default) | SoH @ 8 yr (range) | **R_inc @ 8 yr** | DoD exp at that T |
|---|---|---|---|---|---|
| Passive / air only | 55 | **> 46.2 kWh — does not converge** | 22.0 – 68.6% | **+179.8%** | **−0.40** |
| Basic liquid plate | 48 | **43.3 – 100.1 kWh** | 31.7 – 73.2% | **+101.3%** | +0.25 |
| **Optimised liquid plate** | **40** | **40.6 – 74.6 kWh** | 42.5 – 78.1% | **+50.9%** | +1.00 |
| Immersion *(indicative only — see C13)* | 26 | 37.1 – 53.3 kWh | 59.5 – 85.5% | +14.0% | +0.30 |

**All four rows re-swept under the Naumann default (literal convention), full DoD-exponent × calendar-exponent sweep, linear superposition. No row is carried over from the legacy calibration.** Legacy comparison, for reference only: 46.5–55.8 / 43.1–96.2 / 39.3–62.4 / 35.3–42.7 kWh respectively.

**The 55 °C row is the important one and it is bad news stated plainly.** At 55 °C cell the DoD exponent is **negative (−0.40, the Eldesoky LFP anchor)** — so *shallow* cycling is the **worst** case there, the exact opposite of the 40 °C case. Combined with the linear calendar exponent, the worst corner **exceeds the model's 140 kWh search ceiling and does not converge. At 55 °C cell this duty is not achievable at any pack size the model can search**; the deck's 45 kWh sedan is out by roughly a factor of three. Passive thermal management is not a sizing question at 55 °C — it is a feasibility question.

**Specification: optimised liquid cold plate holding cells ≤40 °C at 45 °C ambient.**

**The band is now too wide to size a 45 kWh-class sedan against its conservative end.** Under the Lewerenz exponent at 40 °C cell the required pack is **74.6 kWh** and year-8 SoH falls to **42.5%**. That is roughly 250 L and ~470 kg of pack — outside the floor pan and the mass budget.

**Three things this document no longer claims:**

- ~~"42 kWh is sufficient at 40 °C cell"~~ — true only at the Naumann exponent and DoD^1.0. Not true at the conservative bound.
- ~~"48 °C cell, accept 66.2–74.9% year-8 SoH"~~ — that band was the legacy Yagci calibration. Under the Naumann default it is 67.9–71.6% at DoD^1.0 across the calendar sweep, and as low as 31.7% across the full sweep.
- ~~"+142% R_inc growth at 48 °C cell"~~ — that figure came from my erroneous renormalised form. The correct Naumann literal value is **+101.3%** (see C15).
- ~~"the ≤40 °C spec is justified on pack size alone"~~ — it is now justified on the **warranty** (C11), which is a stronger argument and a harder constraint.

**What survives, and what to do:** the ≤40 °C cell specification is *more* strongly supported than before, because it is now the difference between an 8-year warranty that is arguable and one that is not. But **the warranty term itself has to enter the design conversation**, and the sizing band has to be presented as 40.6–74.6 kWh at 40 °C rather than as a number.

### Correction to the original 45 kWh figure

The deck states "200 km/day at 75% DoD." Recomputed: 200 km × 12.84 kWh/100 km = 25.68 kWh/day ÷ 45 kWh = **57% DoD**. The 263 km figure corresponds to **90% DoD**. The deck, Proposal and Survey carry three different DoD figures (75%, 76%, 90%) for the same duty.

---

## Item 4 — Delete the charge-rate row

6C on 45 kWh = 270 kW. Indian DC fast chargers run 25–60 kW. The Proposal's own text says "Standard: 1–2C." This vehicle charges overnight on AC at 7–11 kW = 0.15–0.25C.

**Replacement:** "Overnight depot AC charging at 7–11 kW (0.15–0.25C). Full turnaround <8 h from 100% to 20% SoC. Peak DC rate is not a design driver for this duty."

---

## Item 5 — The 45 °C figure, restated on a defensible basis

### Origin

Traced to the rule carried in the corpus papers (hossainlipu2021 line 1173; AI-Enhanced BMS line 427): *"for every 1 °C rise between 30–40 °C, lifespan reduces about two months."*

15 °C × 2 months = 30 months, against 96–120 month nominal life = **25–31%**.

**So "20–30% at 45 °C" is a cumulative LIFETIME figure, not an annual rate.** The deck states it ambiguously beside "94.1% retention after 100 cycles" — opposite magnitudes, and 100 cycles cannot measure a 20–30% effect.

### Correct restatement (Arrhenius, Yagci's measured Ea = 37.3 kJ/mol)

| Cell temperature | Calendar rate vs 35 °C reference |
|---|---|
| 55 °C (passive, 45 °C ambient) | **1.82× faster** |
| 48 °C (basic liquid plate) | 1.35× |
| 40 °C (optimised plate) | 0.95× — reference parity |
| 26 °C (immersion) | 0.48× |

**Suggested deck text:**

> "Passive thermal management in 45 °C ambient raises LFP calendar fade approximately 1.8× against a 35 °C reference. Active cooling sized to hold cells at or below 40 °C returns the pack to reference parity. At this duty, cooling design is worth more than any chemistry substitution."

---

## Item 6 — Supply roadmap: replace the Reliance/Faradion line

### Delete
"Reliance/Faradion supply agreement secured." Appears once in the corpus. No agreement, MOU or offtake exists anywhere. Faradion: £0 operating revenue (2024), ~15 employees, registered office moved Sheffield → London June 2025.

### Verified replacement

| Supplier | Credible 2–3 GWh/yr from | Confidence |
|---|---|---|
| **Exide Energy** (SVOLT LFP; 6 GWh commissioned Sep 2026) | **FY2028** | High — operating plant, Hyundai/Kia PV signed, explicitly open to third parties |
| **Agratas** (Tata, 20 GWh, early 2027 target) | **FY2028–29** | High once Tata captive demand is met |
| **Ola** (1.4 GWh operating) | **FY2029–30** | Medium — cylindrical format mismatch for a sedan pack |
| **Import backstop** (EVE / BYD Blade / CATL) | Available now | Proven at scale; +₹36–45k per pack after BCD expiry (31-Mar-2028) |

Context: total Indian cell output 2026 is ~2–4 GWh. Every 45 kWh pack sold in India today uses imported Chinese cells.

**Action line:** "Lock Exide capacity allocation now — their 6→12 GWh ramp will be fully subscribed by Hyundai/Kia and 2W OEMs by 2028."

---

## Item 7 — Market: the white space exists, but not where the deck says

### Tata Xpres-T EV is losing ground

| | |
|---|---|
| Fleet share | **89% (FY24) → 53% (FY25)** |
| Fleet orders | **26,000 (2023) → ~2,000 (2024), a 92% collapse** after FAME II 4W subsidy expiry |
| Units deployed | 25,000+, 90%+ historic share |
| Battery | 32 kWh (25.5 usable), ARAI 391 km, C75 real-world 240–260 km |
| Price | ₹13.04 L ex-showroom |
| Thermal | Active air cooling; **no documented liquid-cooled battery** |

Documented operator complaints: *"Range dropped by 100 km within 3–4 years"* (Financial Express fleet manager); summer range falling to ~130–140 km on 32 kWh in 45 °C with AC (owner forums); AC-on highway range ~120 km Delhi NCR.

### Operator economics today

At commercial charging tariffs, **EV ≈ CNG on per-km cost (both ~₹3/km), but EV carries ₹3–4 lakh higher capex.** That is the actual reason fleet orders collapsed. About 50% of commercial EV fleets now **lease** rather than buy, to avoid battery and residual risk (Redseer 2025).

### The real gap

| Segment | Unmet need | Evidence | Size |
|---|---|---|---|
| **Airport / intercity** | 400+ L boot + 300+ km real AC range + 100+ km/h | Operators choose BYD E6/EMax 7 for "huge boot" despite cost; BluSmart runs a separate SUV tier | ~5,000–10,000 units/yr |
| **2-shift, 300+ km/day** | Thermal management that survives 2+ fast charges/day without degradation | Operators run 2 shifts to amortise EMI; fast-charge degradation is the documented complaint | ~15,000–20,000 units/yr |
| **Peak summer 45 °C** | Liquid-cooled pack + high-capacity compressor | Universal; Xpres-T has neither | Universal |

**The deck's 400 L boot claim is vindicated — but for the airport/intercity niche, not for mass city ride-hailing.**

### The thermal finding aligns with the model

Xpres-T has no documented liquid-cooled pack. Its most-cited complaint is range loss over 3–4 years. The model shows that at 45 °C ambient with passive thermal management, LFP year-8 SoH falls to **56.8 – 68.1%** and required pack grows to **46.5 – 55.8 kWh** (range across the DoD-exponent × calendar-exponent sweep, C5/8.2). **This is a documented, quantified, unresolved weakness in the market leader — and it is exactly what the model says matters most.**

### Timing risk — the hardest finding

The review lane's view: the fleet EV segment consolidates around 2–3 players by 2028–30, and fleet operators standardise on 1–2 models for maintenance and driver training. On that view a 2034 SOP enters a segment that consolidated years earlier.

**Stated fairly:** this is an interpretation, not a fact. But the underlying evidence is real — Tata's share halved in one year, orders collapsed 92%, and fleet buyers demonstrably consolidate. The deck should address it rather than assume a vacuum persists until 2034.

### Maruti-specific

Maruti's advantage is real and large: **5,100+ service touchpoints across 2,300 cities — the largest in India**, plus 2,000+ exclusive charging points and 13 CPO partners. But the e-Vitara at ₹20–25 L is the wrong product and price for fleet. The Suzuki President has said compact vehicles are best suited to EV and hinted at a small-car EV with no timeline.

**Maruti entering this segment below ₹12 L would disrupt Xpres-T directly.** That is a genuine argument for the programme existing — but it argues for earlier, not 2034.

---

## Item 8 — Peer-reviewed aging evidence: what changed and what it does not license

Three peer-reviewed papers were folded into the model. Each one **narrowed or reversed** an existing assumption rather than confirming the deck. The honest summary is that the case got weaker, and better evidenced.

### 8.1 The three first-round papers, and exactly what each does and does not support

> **SUPERSEDED IN PART BY 8.6–8.9.** Sections 8.1 and 8.2 describe the **1st-rework legacy 'Yagci' calibration**. The default calibration is now Naumann 2018 and the sweeps are wider. Retained unaltered for traceability: every number below still reproduces exactly from model sections [1]–[11].

#### Gasper et al. 2021 — the calendar time exponent is ~0.45, not 0.5

> Gasper, P., Gopalakrishnan, S., Finegan, D., Zhang, Z., Sprenger, R., "Calendar Aging of NMC and LFP Cathode Cells: Establishing the Power-law Relationship between Calendar Fade and Time", *Journal of the Electrochemical Society* (2021).
>
> **⚠ CITATION INCOMPLETE — DO NOT SUBMIT EXTERNALLY.** The volume/article number (168, 020502) and both candidate DOIs (`…/abd7a8`, `…/abeb5f`) **failed verification** against Crossref and doi.org. **JES vol. 168 art. 020502 (Feb 2021) is a different paper** — *"Challenging Practices of Algebraic Battery Life Models…"*, DOI 10.1149/1945-7111/abdde1. Author list and year above are unverified. **See C16.** The finding below is used only as a screening input to the calendar exponent sweep and is **not load-bearing**.

**Supports:** a re-analysis of 17 independent calendar-aging datasets in which a fixed t^0.5 fade is **statistically invalid** — only **1 of 17** series contained an exponent of 0.5 within its own 95% confidence interval. The pooled exponent converges to **~0.45**, and √t **overpredicts** long-term fade. The model now parameterises the exponent. *(1st-rework sweep was 0.40 / 0.45 / 0.50; the 2nd-rework sweep is 0.45 / 0.50 / 0.75 / 1.00 — see C10, because Lewerenz 2017 measures 1.00 on LFP.)*

**Does not support:** using 0.40 at our operating point. The same paper finds the exponent **rises back toward 0.5 as temperature increases**. At a 40–48 °C cell the plausible range is therefore 0.45–0.50, and the 0.40 column is an optimistic tail, not a central case. **This is now superseded: Lewerenz 2017 measures a linear exponent of 1.00 on LFP at 25–40 °C, so the defensible range is 0.45–1.00 and the conservative bound is 1.00. See C10.**

**Net effect on the spec:** small but one-directional. The 0.45 and 0.40 rows are *smaller* packs than 0.50, so relaxing √t makes the original 44 kWh figure look better — which is exactly why it should not be taken at face value without the temperature qualifier attached. *(Superseded: under the full 0.45–1.00 sweep the calendar axis widens the 48 °C band to 43.3–100.1 kWh. See 8.8.)*

#### Schreiber et al. 2025 — linear DoD scaling of cycle rate is REFUTED

> Schreiber, D., et al., *Journal of Energy Storage* **112**, 115357 (2025). DOI [10.1016/j.est.2025.115357](https://doi.org/10.1016/j.est.2025.115357)

**Supports:** the model scaled `k_cyc` linearly with DoD. Schreiber's commuter-vs-highway comparison refutes this in the linear phase — *"the commuter and highway scenarios [age] approximately at a comparable pace"* — with an **8% DoD window and an 80% DoD window showing similar per-EFC degradation.** The DoD effect is **sub-linear or threshold-dependent, not proportional.** The model now sweeps DoD exponent **1.0 / 0.5 / 0.0**.

**Does not support — and this is the critical caveat:**

| | Schreiber 2025 | MACH1 requirement |
|---|---|---|
| Chemistry | **NMC/graphite (LG E78)** | **LFP** |
| Temperature | **constant 20 °C only** | **40–48 °C cell** |
| Temperature data in paper | **none** | Arrhenius term required |

The paper **contains no temperature data at all**, so it **cannot calibrate an Arrhenius term.** Extrapolating its DoD result to a 40–48 °C LFP cell is an unsupported step, not a conservative one.

Its NMC-specific mechanisms also **do not transfer** to LFP: transition-metal dissolution, rock-salt-layer formation, and LAM_PE from charging to 4.19 V. None of these are LFP degradation modes.

**Verdict: the DoD MECHANISM insight partially transfers. The DoD MAGNITUDE does not.** Treat DoD exponent 0.5 and 0.0 as bounding a *structure* we have not yet measured for LFP — not as calibrated values.

**Net effect on the spec:** material and adverse. Moving from DoD^1.0 to DoD^0.0 raises the 48 °C pack from 44.0 to 47.9 kWh (**+9.0%**) and drops year-8 SoH from 72.1% to 66.2% (**−5.9 pp**).

**Outstanding:** LFP-specific DoD data. No dataset in hand measures per-EFC rate against DoD at 40–48 °C. Candidates to mine or replicate: **Louli & Dahn, *J. Power Sources* 2019, art. A3031**; **Eldesoky et al., 2020 (LFP)**. Until one of those closes this, the DoD axis is **the largest single unquantified lever in the model.**

#### Graner et al. 2026 — prediction uncertainty is far larger than assumed

> Graner, M., et al., arXiv:2609.10185 (2026).

**Supports:** an explicit structural-uncertainty band on the 8-year EOL claim. See 8.3.

### 8.2 Consolidated sweep — LEGACY 'Yagci' calibration (superseded by 8.8)

> **LEGACY CALIBRATION.** Ea 37.3 kJ/mol, SOC factor 0.75, calendar sweep 0.40–0.50, DoD sweep 0.0–1.0. **Not the default any more.** Reproduces exactly from model sections [1]–[11].

**48 °C cell — liquid_plate, the realistic case**

| DoD exponent | cal exp | Pack (kWh) | EFC @ yr 8 | SoH @ yr 8 |
|---|---|---|---|---|
| 1.00 | 0.40 | 42.3 | 1618 | 74.9% |
| 1.00 | 0.45 | 43.1 | 1589 | 73.6% |
| 1.00 | 0.50 | 44.0 | 1557 | 72.1% |
| 0.50 | 0.40 | 43.8 | 1565 | 72.5% |
| 0.50 | 0.45 | 44.6 | 1536 | 71.1% |
| 0.50 | 0.50 | 45.6 | 1503 | 69.6% |
| 0.00 | 0.40 | 45.9 | 1493 | 69.1% |
| 0.00 | 0.45 | 46.8 | 1462 | 67.7% |
| 0.00 | 0.50 | **47.9** | 1429 | **66.2%** |

**40 °C cell — plate_opt, requires a PROVEN chiller loop**

| DoD exponent | cal exp | Pack (kWh) | EFC @ yr 8 | SoH @ yr 8 |
|---|---|---|---|---|
| 1.00 | 0.40 | 38.9 | 1762 | 81.6% |
| 1.00 | 0.45 | 39.3 | 1741 | 80.6% |
| 1.00 | 0.50 | 39.9 | 1717 | 79.5% |
| 0.50 | 0.40 | 39.7 | 1724 | 79.8% |
| 0.50 | 0.45 | 40.2 | 1702 | 78.8% |
| 0.50 | 0.50 | 40.8 | 1678 | 77.7% |
| 0.00 | 0.40 | 40.9 | 1674 | 77.5% |
| 0.00 | 0.45 | 41.5 | 1652 | 76.5% |
| 0.00 | 0.50 | **42.1** | 1627 | **75.3%** |

Note the direction of both axes: **more DoD-exponent reduction → larger pack; lower calendar exponent → smaller pack.** At 48 °C cell the pack band is dominated by the **DoD axis (3.9 kWh spread, holding calendar exponent at 0.50)** over the **calendar axis (1.7 kWh spread, holding DoD exponent at 1.00)** — a factor of roughly 2.3. That is the quantitative basis for calling the DoD gap the priority.

### 8.3 Graner structural-uncertainty band on the 8-year EOL claim

Graner et al. worked on the **same LFP/graphite chemistry family** (Naumann data, Sony/Murata 3 Ah), with **36 replicated laboratory conditions** and **5.2 years of field validation** on a residential HESS.

Their measured uncertainty:

| Graner finding | Figure |
|---|---|
| Full predicted EOL range | **~3 years on a 12.3-year mean (~33%)** |
| Mean difference between min and max **stress scenarios alone** | **10 months** |
| Spread from **one outlier cell** at one frequently-visited condition (25 °C / 100% SOC) | **5.9% — driving ~50% of the entire EOL range** |
| Same range with that outlier replaced | **3 yr → 1.5 yr (halved)** |
| Replication 3 → 6 cells, spread uncertainty | **~50% → ~32%**, by 1/√(2(n−1)) |

**Their stated lower bound for a much sparser case than theirs — ours:**

> *"A minimum 40-50% EOL range (3.2-4.0 years on an 8-year prediction) is the lower bound implied by this paper."*

**Applied to the 8-year claim:**

| | Value |
|---|---|
| Point claim (model) | **8.0 yr** |
| Graner structural band | **3.2 – 4.0 yr** |
| Equivalently | EOL arrives at **40–50%** of predicted life = **50–60% of life lost** |

**Why this is a LOWER BOUND for MACH1 and not an estimate:**

- Graner had **36 replicated lab conditions. We have 0.** Our entire cycling basis is one manufacturer's datasheet line (EVE LF105).
- Our calendar basis is **one anchor** (Yagci 2025, a single protocol). Graner tested 36.
- Their 3-cell conditions sit near the worst case of the 1/√(2(n−1)) replication curve — the very term that dominates their reported spread.
- **One** cell at **one** condition produced ~50% of their whole EOL range. In a dataset with no replication, a single such cell is not detectable, let alone removable.
- Their duty was residential HESS. Ours is an EV duty cycle with 1–2 fast charges per shift — a harder duty, not an easier one.

**This band is reported ALONGSIDE the parameter sweeps and is NOT merged into them.** Applying it to the point estimates in 8.2 would double-count the uncertainty already carried by the sweep. It answers a different question: *not* "which parameter values are defensible" but "how wrong could the whole model be even if every parameter were right."

**Consequence for the proposal: do not present "8-year pack life" as a point claim.** Present it as a modelled expectation with a 3.2–4.0 yr structural band and an explicit statement that closing that band requires the programme in 8.5.

### 8.4 DESIGN REQUIREMENT — charge-window and rest policy (from Schreiber's knee-point finding)

Schreiber's DoD result does not come from a smooth power law. Divergence appears **later**, at a **knee point**, triggered by three conditions occurring **together**:

1. **Sustained low-SOC-window cycling** — cell repeatedly taken below ~3.25 V
2. **High charge rate**
3. **Omitted rest periods**

The mechanism is inhomogeneous lithiation producing **LAM_NE and lithium plating.** These are LFP-relevant mechanisms, which is why this requirement transfers even though the DoD magnitude does not (8.1).

**This is a requirement on the BMS and charging strategy, not commentary.**

> **REQUIREMENT CW-1 — SoC floor.** The BMS shall enforce a **discharge SoC floor of 25%** under all normal depot and en-route operation, with the reserve layer inaccessible to the driver. The pack shall not be cycled below **3.25 V** cell voltage under any normal charge–discharge event.
>
> **REQUIREMENT CW-2 — Charge-window policy.** Opportunity charging shall operate within a **30–90% SoC window** at a maximum **0.5C**. A sustained low-SOC-window discharge event combined with a charge above 0.5C shall be flagged by the BMS as a prohibited combination.
>
> **REQUIREMENT CW-3 — Mandatory rest/relaxation.** After **two** consecutive charge events within a 24-hour shift, a **minimum 30-minute rest period at ≥40% SoC** shall be enforced before further charging. The BMS shall log and enforce this; it shall not be driver-defeatable.
>
> **REQUIREMENT CW-4 — Interleaving prohibition.** A charge event shall not be initiated while cell voltage is below **3.25 V**. Below that threshold the BMS shall hold charge until relaxation brings the cell above it.
>
> **REQUIREMENT CW-5 — Verification.** The pack shall demonstrate compliance with CW-1 to CW-4 over a minimum **500-cycle** instrumented validation, reporting per-event cell-minimum voltage, charge rate, and rest-period compliance.

The business case is small: at 0.15–0.25C overnight depot duty (Item 4), CW-1 to CW-4 cost essentially nothing in charge time and buy insurance against the one degradation mode in the whole model that has an identified physical trigger.

### 8.5 RECOMMENDED VALIDATION PROGRAMME — what would actually close the gap

**Proposal content. This is the line item that converts an 8-year claim into a defensible one.**

Graner's finding is precise and actionable: **replication is what buys certainty, and one bad cell can dominate the entire answer.** That argues for a specific, cheap, targeted programme rather than a broad one.

> **PROPOSED TEST MATRIX — LFP calendar/cycle ageing, 6-cell replication**
>
> | Parameter | Specification | Why |
> |---|---|---|
> | Cells | **6 identical prismatic LFP**, same lot | 3→6 replication cuts spread uncertainty from **~50% to ~32%** (1/√(2(n−1))) |
> | Temperature | **40–45 °C**, controlled ±1 °C | Matches the MACH1 operating cell temperature, and is the band where Gasper puts the calendar exponent at 0.45–0.50 |
> | SoC | **90–100%**, held | Worst-case calendar ageing; also the condition where Graner's outlier appeared |
> | Mode | **Calendar ageing**, periodic capacity check | Isolates the calendar term, which is currently anchored to a single Yagci protocol |
> | Duration | to 80% SoH or 24 months, whichever first | Yields the calendar exponent directly, replacing the √t assumption with a measured value |
> | **Second arm** | **DoD ladder: 20% / 50% / 80% windows at the same T and SoC** | **This is the test that closes the Schreiber gap for LFP** — it measures the DoD exponent our model currently only sweeps |
>
> **Cells tested per arm: 6, not 3.** Budget the extra 3 cells. Graner's 3-cell conditions sit at ~50% spread uncertainty; 6 cells bring that to ~32%.

**Which gap does each arm close, and by how much:**

| Gap | Closed by | Expected gain |
|---|---|---|
| Calendar exponent assumed √t | **Arm 1** (40–45 °C, 90–100% SoH calendar ageing) | Replaces a **30.1 kWh-wide** assumed axis (40 °C cell) with a *measured* exponent at the operating temperature. This is now the highest-value arm in the programme. |
| DoD exponent assumed proportional | **Arm 2** (DoD ladder) | Collapses a **3.9 kWh-wide** assumed axis into a measurement. **This is the single largest uncertainty in the model** and the only arm that addresses it. |
| Structural 40–50% band | **6-cell replication on both arms** | Graner's own arithmetic: **~50% → ~32%** spread uncertainty. Does not close the band; it **narrows** it, and it makes a future outlier *detectable and replaceable* — which by itself halved their range when applied. |
| Cell temperature assumed, not simulated | Pack thermal model (separate workstream) | No cell-level test closes this. Requires simulation plus instrumented vehicle trial. |

**Stated plainly: this programme does not validate the 8-year claim. It removes two of the three largest assumed parameters and takes the structural band from ~50% toward ~32%.** The residual band after Arm 1 + Arm 2 + 6-cell replication is still wider than the 8-year point claim. That is the honest position, and it is a stronger proposal than quoting a single number.

### 8.6 The five papers added in the second rework

| Paper | What it changed | Does it license? |
|---|---|---|
| **Naumann et al. 2018**, J. Energy Storage 17, 153–169. DOI 10.1016/j.est.2018.05.006 | Became the **default calendar calibration**. Ea 17.126 kJ/mol, SOC factor **0.613954** (literal, Eq. 3+6) | A purpose-built LFP calendar fit on a 3 Ah cell, 885 days, 17 TPs × 3 cells, <2.2% error on Q_loss. But **Arrhenius fitted at 25/40/60 °C only** (8.7) |
| **Lewerenz et al. 2017**, J. Power Sources 345, 254–263 | **Refutes the √t calendar law on LFP.** Linear fade, exponent 1.0 | 50 × 8 Ah LFP cells, >2 years, >25 check-ups, passive-electrode effect corrected out. **But reports no fitted Ea** — temperature extrapolation borrows Naumann's. Its own conclusion ("3–4 years to 80% at 40 °C") is the single most consequential sentence in this document |
| **Eldesoky/Simolka et al. 2020**, J. Appl. Electrochem. 50, 1101–1117. DOI 10.1007/s10800-020-01465-6 | Established a **negative** DoD exponent at 55 °C | LFP at 55 °C and −20 °C with post-mortem AFM/SEM/EDX/XPS. The −0.40 exponent is recomputed from the paper's own EOL percentages (16.5% vs 12.5% → 1.32). **Its absolute %/EFC figures are NOT traceable to this paper's text** — they belong to a figure reproduced from ref [26]. Only the ratio is used |
| **Waldmann et al. 2014**, J. Power Sources 262, 129–135 | Set the **25 °C mechanism-crossover floor** | Two Arrhenius regimes, both R² = 0.99, proven post-mortem. **But it is NMC/LMO blend and CYCLE ageing at 1C, not LFP calendar** — its 36.66 kJ/mol is *not* a like-for-like comparison with Naumann's 17.126 and the near-match is coincidental |
| **Pozzato et al. 2023**, Joule 7, 2035–2053 | Forced the **SoH reference-temperature requirement** | **One** NMC vehicle, **one** year, ~3,750 h, mild maritime climate, chemistry not even stated in the paper. **A caution, not a transferable calibration.** Valuable only for showing measured SoH is temperature-dependent and partly reversible |

### 8.7 The Naumann normalisation question — RESOLVED (see C15)

Naumann's Eq. (6) divides `kSOC;Q(SOCref=100%)` out of `kref`, and the paper states the SOC factors "CAN BE SET TO A VALUE OF 1 because kref is defined with SOCref = 100%". **The literal reading is correct** and is now the default: multiply by `kSOC(SOC) = 0.613954` at 66% SOC.

| Convention | Q_loss factor | A_cal (48 °C, 66% SOC) | 8-yr fade | R_inc factor | R_inc @ 8 yr |
|---|---|---|---|---|---|
| **LITERAL — Eq. 3+6 as written (DEFAULT)** | **0.613954** | **7.1088 %/√yr** | **20.1%** | **1.473608** | **+101.3%** |
| Renormalised by the 66%/100% ratio (my earlier error) | 0.639911 | 7.4094 %/√yr | 21.0% | 2.067280 | +142.1% |
| Error introduced | +4.06% | | +0.9 pp | **+28.72%** | **+40.8 pp** |

The renormalised form is retained behind `NAUMANN_SOC_CONVENTION` **solely** so the error stays reproducible. It is not what the paper's equations say, and it must not be used for any reported figure. The same 28.72% correction applies to R_inc as to nothing else in this document — it is the single largest arithmetic error found in this work, and it came from a claim I made ("algebraically identical") that was false.

### 8.8 Consolidated sweep under the new default (Naumann 2018, literal convention)

**48 °C cell** — linear superposition, 10% EOL reserve:

| DoD exp | cal exp | Pack (kWh) | EFC @ yr 8 | SoH @ yr 8 | R_inc @ yr 8 |
|---|---|---|---|---|---|
| -0.40 | 0.45 | 50.0 | 1371 | 63.5% | 101.3% |
| -0.40 | 0.50 | 51.3 | 1335 | 61.8% | 101.3% |
| -0.40 | 0.75 | 62.9 | 1089 | 50.4% | 101.3% |
| -0.40 | 1.00 | 100.1 | 684 | 31.7% | 101.3% |
| +0.00 | 0.45 | 47.1 | 1454 | 67.3% | 101.3% |
| +0.00 | 0.50 | 48.3 | 1419 | 65.7% | 101.3% |
| +0.00 | 0.75 | 58.0 | 1182 | 54.7% | 101.3% |
| +0.00 | 1.00 | 87.6 | 782 | 36.2% | 101.3% |
| +0.25 | 0.45 | 45.9 | 1493 | 69.1% | 101.3% |
| +0.25 | 0.50 | 46.9 | 1460 | 67.6% | 101.3% |
| +0.25 | 0.75 | 55.9 | 1224 | 56.7% | 101.3% |
| +0.25 | 1.00 | 83.2 | 824 | 38.1% | 101.3% |
| +0.50 | 0.45 | 44.8 | 1527 | 70.7% | 101.3% |
| +0.50 | 0.50 | 45.9 | 1493 | 69.1% | 101.3% |
| +0.50 | 0.75 | 54.4 | 1259 | 58.3% | 101.3% |
| +0.50 | 1.00 | 80.1 | 855 | 39.6% | 101.3% |
| +1.00 | 0.45 | 43.3 | 1581 | 73.2% | 101.3% |
| +1.00 | 0.50 | 44.2 | 1548 | 71.6% | 101.3% |
| +1.00 | 0.75 | 52.1 | 1313 | 60.8% | 101.3% |
| +1.00 | 1.00 | 76.1 | 900 | 41.7% | 101.3% |

**40 °C cell**:

| DoD exp | cal exp | Pack (kWh) | EFC @ yr 8 | SoH @ yr 8 | R_inc @ yr 8 |
|---|---|---|---|---|---|
| -0.40 | 0.45 | 44.5 | 1540 | 71.3% | 50.9% |
| -0.40 | 0.50 | 45.4 | 1508 | 69.8% | 50.9% |
| -0.40 | 0.75 | 53.2 | 1286 | 59.5% | 50.9% |
| -0.40 | 1.00 | 74.6 | 918 | 42.5% | 50.9% |
| +0.00 | 0.45 | 42.9 | 1596 | 73.9% | 50.9% |
| +0.00 | 0.50 | 43.8 | 1565 | 72.4% | 50.9% |
| +0.00 | 0.75 | 50.7 | 1350 | 62.5% | 50.9% |
| +0.00 | 1.00 | 69.2 | 990 | 45.8% | 50.9% |
| +0.25 | 0.45 | 42.2 | 1624 | 75.2% | 50.9% |
| +0.25 | 0.50 | 43.0 | 1593 | 73.8% | 50.9% |
| +0.25 | 0.75 | 49.6 | 1381 | 63.9% | 50.9% |
| +0.25 | 1.00 | 67.0 | 1022 | 47.3% | 50.9% |
| +0.50 | 0.45 | 41.6 | 1648 | 76.3% | 50.9% |
| +0.50 | 0.50 | 42.3 | 1617 | 74.9% | 50.9% |
| +0.50 | 0.75 | 48.7 | 1407 | 65.1% | 50.9% |
| +0.50 | 1.00 | 65.4 | 1047 | 48.5% | 50.9% |
| +1.00 | 0.45 | 40.6 | 1687 | 78.1% | 50.9% |
| +1.00 | 0.50 | 41.3 | 1657 | 76.7% | 50.9% |
| +1.00 | 0.75 | 47.3 | 1448 | 67.0% | 50.9% |
| +1.00 | 1.00 | 63.1 | 1084 | 50.2% | 50.9% |

**Envelopes: 48 °C → 43.3–100.1 kWh, SoH 31.7–73.2%. 40 °C → 40.6–74.6 kWh, SoH 42.5–78.1%.** The band is dominated by the **calendar exponent** rather than the DoD exponent — a reversal of the first rework, because Lewerenz's linear law is so much more severe than Naumann's √t. Axis widths, each holding the other axis at its extreme: at 40 °C the DoD axis spans **11.5 kWh** and the calendar axis **30.1 kWh**; at 48 °C, **24.0** vs **50.1 kWh**; at 55 °C, **46.0** vs **83.2 kWh**.

### 8.9 Pack size vs cell temperature with the DoD exponent interpolated

| Cell temp | Interpolated DoD exp | Pack (kWh) | SoH @ 8 yr | R_inc @ 8 yr | Basis |
|---|---|---|---|---|---|
| 40 °C | +1.00 | 41.3 | 76.7% | 50.9% | **ANCHOR** — Gauthier 2022 (NMC622) |
| 44 °C | +0.62 | 43.6 | 72.7% | 72.1% | interpolated |
| 48 °C | +0.25 | 46.9 | 67.6% | 101.3% | ***ASSUMED — NOT MEASURED*** |
| 52 °C | -0.12 | 52.1 | 60.8% | 141.0% | interpolated |
| 55 °C | -0.40 | 58.7 | 54.0% | 179.8% | **ANCHOR** — Eldesoky 2020 (LFP) |

**Pack sensitivity to DoD scaling, holding DoD exponent free** (Naumann default, cal exp 0.50):

| Cell temp | −0.40 | 0.00 | +0.25 | +0.50 | +1.00 |
|---|---|---|---|---|---|
| 40 °C | 45.4 | 43.8 | 43.0 | 42.3 | 41.3 |
| 44 °C | 48.1 | 45.8 | 44.8 | 44.0 | 42.7 |
| 48 °C | 51.3 | 48.3 | 46.9 | 45.9 | 44.2 |
| 52 °C | 55.2 | 51.1 | 49.3 | 48.0 | 46.0 |
| 55 °C | 58.7 | 53.5 | 51.4 | 49.7 | 47.4 |
**Read across each row:** the pack spread from the DoD exponent alone is **4.1 kWh at 40 °C**, 5.4 at 44 °C, 7.0 at 48 °C, 9.2 at 52 °C and **11.3 kWh at 55 °C**. Read down the +1.00 column against the interpolated value at each temperature and the picture is the same: **because the interpolated exponent passes through ≈0 at our operating point, DoD-scaling sensitivity is lowest exactly where we operate and largest at both ends of the bracket.**

**And the honest caveat:** the interpolation *between* 40 °C (+1.00) and 55 °C (−0.40) — which contains our operating point — rests on the 48 °C anchor, and that anchor has **no measurement behind it**. The encouraging conclusion is real but it is resting on the weakest point in the curve. **No single DoD exponent is defensible from the available evidence.**

### 8.10 WARRANTY-DEFINITION REQUIREMENTS (from Pozzato 2023)

Pozzato et al. logged a single Audi e-tron over ~3,750 h and found, verbatim:

> *"the available capacity as estimated by the BMS changes over time and recovers after a few months resting period (attributed to the COVID-19 pandemic lockdown) … we postulate that the capacity recovery is due to a combination of higher environmental temperatures, which lead to increased available capacity, and rejuvenation due to the long period of storage."*

> *"for the first year of EV operation, this work shows that indicators are affected by temperature, which outwins time effects."*

> *"(2) SoH algorithms from laboratories may falter in the field"* … EKF *"can very well lose accuracy or even diverge when deployed on the field"* … *"datasets collected in the laboratory can be partially, or not at all, representative of real-world operating conditions."*

**Measured SoH is temperature-dependent and partly reversible. A linear fade model — which is what this whole model is — will misread it.**

> **REQUIREMENT WD-1 — Reference temperature.** All SoH figures, in this document and in any customer-facing warranty, shall be reported at a **defined reference temperature (proposed: 25 °C cell)**, not at ambient. Without this, a year-8 SoH claim is **not comparable** between packs, between vehicles, or between test programmes. Pozzato shows ambient-referenced SoH moves with the weather.
>
> **REQUIREMENT WD-2 — Thermal preconditioning.** The warranty test protocol shall include a **mandatory thermal preconditioning step — a defined soak at the reference temperature until cell ΔT < 2 K — before every capacity measurement.** Without it, the measurement mixes ageing with ambient conditions.
>
> **REQUIREMENT WD-3 — Rest-state recording.** Every SoH measurement shall be accompanied by a **rest-state log** (time since last charge, storage temperature, storage duration). Pozzato's "recovery" is a rest-and-warm artefact; a warranty claim that cannot distinguish a genuine recovery from a measurement artefact is not defensible.
>
> **REQUIREMENT WD-4 — Peak power warranted separately.** Per C9, an 8-year/80%-**capacity** warranty says nothing about **power**. At 48 °C cell, Naumann implies +101.3% R_inc by year 8 (peak power ~50% of new). Peak-power and DC-charge-acceptance limits shall be warranted as a **separate, separately-measured term**.

**Scope of the evidence — do not overread it.** One vehicle. One year. ~3,750 h. NMC. A mild maritime climate, nothing like 45 °C Bangalore/Gurgaon. The paper does not even state the chemistry. **Pozzato is a caution about how to define a warranty, not a calibration for one.** It cannot be used to set an SoH number for a 45 kWh LFP pack.

---

## Cross-document errors corrected

| Claim in deck | Correct value | Consequence |
|---|---|---|
| "365 EFC/yr" | **190–228 EFC/yr** (base, 45 kWh) | 3,000 cycles = 15.8 yr, not 8.2. Deck over-counts cycles ~1.9× |
| HVAC 14.80 kWh/day | **6.62 kWh/day** | Deck overstates by **2.24×** — ~8 kWh/day of phantom energy in every range figure |
| "Tata Dire Tour S" is the fleet EV being displaced | **Does not exist.** The fleet EV is **Xpres-T EV**; Dzire Tour S is the CNG petrol car | Competitive analysis aimed at a non-existent product |
| "BluSmart" as anchor customer | **Paused operations April 2025** (Gensol/SEBI fund-diversion), ~8,000 cars | Not a credible 50–70k unit/year anchor |
| "Kharkhoda plant tooled for production" | Phase 1 is building the **Brezza (ICE)** on a multi-model line; e-Vitara is built at Hansalpur | Conflates vehicle assembly with cell manufacturing |
| "Charging via Reliance New Energy already in place" | That is battery manufacturing. Charging is **Jio-bp** + Maruti's dealer network | Two different businesses |
| Service network "3,614 workshops" | **2016 data.** Current: 5,926 touchpoints, 1,500 distributor touchpoints | Ten-year-old figure |
| "₹11/km net fare" | Gross fare. Net after 25–28% commission + deadhead ≈ **₹7.3/km** | Symmetric across EV and CNG, so the comparison survives — but absolute take-home figures are meaningless |

---

## Model limitations

- **The default calibration is Naumann 2018** (C8). Its Arrhenius term was fitted at **25/40/60 °C only**, so the 35 °C anchor and the whole curve are interpolated between three points. Its SOC normalisation is the **literal** Eq. 3+6 form, ×0.613954 for Q_loss and ×1.473608 for R_inc (8.7, C15).
- **The calendar time exponent is contested across LFP studies, 0.45 to 1.00** (C10). Gasper ~0.45 is an inference across NMC+LFP **whose citation is incomplete and must not be submitted** (C16); Naumann 0.50 is an LFP fit; **Lewerenz 1.00 is a direct LFP measurement at our operating temperature and is the conservative bound.** 0.50 is not a central estimate. This axis now dominates the pack band (**30.1 kWh at 40 °C, 50.1 kWh at 48 °C**).
- **Lewerenz reports no fitted Ea.** Every Lewerenz number outside 40 °C is a two-source extrapolation borrowing Naumann's 17.126 kJ/mol.
- **Resistance growth is a separate warranty exposure and is not covered by the pack-size claim** (C9). Ea;R = 71.827 kJ/mol is 4.2× the capacity Ea and R_inc is linear in t. **Naumann and Lewerenz directly contradict each other on this** and it cannot be settled from the papers in hand.
- **The DoD exponent sweeps −0.40 to +1.00 and changes sign with temperature** (C12). The 48 °C anchor is **an assumption with no measurement behind it**, and it is the point we operate at. The curve mixes NMC, NMC622, LFP and assumption, and is an interpolation, not a fit.
- **25 °C cell is a hard modelling floor** (C13). Below it the Arrhenius sign inverts to Li plating. `solve_min_pack()` raises. **The immersion scenario at 26 °C is 1 °C above a mechanism change and is indicative only.**
- Linear superposition of calendar + cycle fade. Conservative; RSS raises year-8 SoH 5.9–10.4 pp at the two specified cell temperatures.
- `k_cyc` still rests on a **manufacturer datasheet line** (EVE LF105: 2,000 cycles to 80% at 45 °C, 0.5C/0.5C, 100% DoD). That is the only cycling data in hand.
- **LFP-specific DoD data at 40–48 °C remains outstanding.** Closest available: Gauthier 2022 (NMC622), Eldesoky 2020 (LFP but 55 °C), Louli & Dahn 2019 (**not held**).
- **Cell temperatures are assumed, not simulated.** A pack thermal model is required. No cell-level test closes this.
- **SoH measured at ambient is not a stable quantity** (8.10). Pozzato shows apparent recovery with rest and temperature. All comparisons here are model outputs at a fixed reference, not field measurements.
- **The 8-year EOL claim carries a 40–50% structural band (3.2–4.0 yr)** per Graner 2026, stated there as a **lower bound** for our sparser case. Reported separately, not merged into the parameter sweeps.
- **Sweep band: 40.6–74.6 kWh at 40 °C cell, 43.3–100.1 kWh at 48 °C cell, and non-convergent (>140 kWh) at 55 °C cell.** The band's upper end exceeds what a 45 kWh-class sedan floor pan can hold. **This document no longer supports a single pack-size claim.**

---

## Still open

- **Item 2** — chemistry-agnostic pack architecture evidence lane in flight.
- **Motor durability** — the deck's own motor rated life is 200,000 km against a 480,000 km duty. Expires at 3.3 years, mid-loan. Unaddressed in every source document.
- **Item 8.5 validation programme** — not yet costed or scheduled. Arms 1 and 2 are now *more* necessary, not less: the calendar exponent axis (C10) is larger than the DoD axis it was meant to close.
- **Warranty structure** — under the Lewerenz exponent, 8-year/80% is not reachable at 40 °C cell (C11). **This needs a product decision, not more modelling.**
- **R_inc conflict** — Naumann 71.827 kJ/mol vs Lewerenz "hardly influenced". Unresolvable from papers in hand.
- **Louli & Dahn 2019, JES 166 A3031** — not held. Outstanding.
- **Gasper 2021 DOI unverified** — confirm before external use.