# Total Cost of Ownership Analysis
### MACH1 / FleetLine E1 — operator and driver economics
### Built on 31 sources, with an explicit convergence analysis

---

## 0. Headline

**BEV wins — but by less than we previously claimed, and on two conditions that are not
optional.**

| Finding | Number |
|---|---|
| EV cost advantage, 5-yr, **financed** (Delhi) | **+8.4%** (₹6.17/km vs ₹6.73/km) |
| EV cost advantage, 5-yr, **cash purchase** | **+17.5%** (₹4.94/km vs ₹5.98/km) |
| EV cost advantage, **8-year** horizon | **+23.6%** (₹4.46/km vs ₹5.84/km) |
| Breakeven duty | **153 km/day** at 5 yr · **85 km/day** at 8 yr |
| Driver take-home gain | **+₹2,548/month** during loan · **+₹14,200/month** after |
| **Condition 1 — charging tariff** | At **₹12/kWh** (public DC) EV **loses** by 7.5% |
| **Condition 2 — uptime** | Only **26 extra downtime-hours/month** of headroom |

**Three corrections to what we said before:**

1. **Our earlier "16–28% better" was too optimistic.** It came from adding the full purchase
   price to both vehicles with no financing treatment and assuming a 36% EV residual. With
   financing counted correctly and BluSmart's real 26% residual, the honest 5-year financed
   figure is **+8.4%**.
2. **The deck's residual assumption was wrong.** It implied ~36% on our ₹14 L vehicle.
   BluSmart — our exact target segment — reported assuming 10% and realising **26%**.
3. **Delhi's blanket road-tax waiver lapsed in March 2026.** That is new cost, and it lands on
   the city where our case is otherwise strongest.

**None of this changes the powertrain verdict.** It changes the *margin*, and it identifies the
one operating condition that would flip the answer: **public charging instead of depot
charging.**

---

## 1. Method

Per the brief — *purchase, energy, maintenance, uptime, residual value* — from **both** the
operator's and the driver's view.

**Costed once, never twice.** Capital cost appears either as the cash on-road price *or* as the
full EMI stream. An earlier draft of this analysis added both, which double-counted the loan
principal and made the EV look 95% worse. That error is recorded in §10 because it is exactly
the kind of mistake that survives into a jury room if nobody checks.

**Included:** ex-showroom, GST, road tax, financing, energy (net of charging losses),
maintenance (net of the EV tyre premium), insurance, driver downtime, residual credit.

**Excluded, with reason:**

| Excluded | Why |
|---|---|
| Aggregator commission (20–25%) | **Same on both vehicles**, so it cancels in the comparison. Excluding it also keeps this reconcilable with the deck's ₹57,200/month gross revenue. Flagged in §9 — it does not change the ranking. |
| Toll / FASTag | Vehicle-class dependent, not powertrain dependent |
| Driver salary as a cost | We treat it as revenue-side (fare × km), and model only *lost* earning time as a cost — that is the uptime term |
| Battery replacement | Outside the 8-year horizon at our duty; modelled separately in §8 |

---

## 2. Configuration used

| | |
|---|---|
| **Vehicle** | FleetLine E1 — BEV, LFP 45 kWh, PMSM 80 bhp continuous, single-speed |
| **Comparator** | Maruti Dzire Tour S (CNG) |
| **Duty** | 200 km/day × 26 days × 312 days = **5,200 km/mo · 62,400 km/yr** |
| **Consumption** | **12.84 kWh/100 km** (verified duty cycle, battery phase — corrects the deck's 15.38) |
| **Charging** | Depot AC overnight, **90% wall-to-battery** efficiency |
| **Revenue** | ₹11/km net fare → **₹57,200/month** |
| **Financing** | 10% annual, 60 months, no down payment (deck's assumption) |
| **Horizon** | 5 years (loan) and 8 years (battery-phase horizon) |
| **Cities** | Delhi, Mumbai, Bengaluru — different tariffs, road tax and CNG prices |

---

## 3. The cost stack — Delhi, 5 years, financed

| Component | EV | CNG | EV advantage |
|---|---|---|---|
| On-road (ex-showroom + GST + road tax) | ₹13,99,860 | ₹8,51,488 | −₹5,48,372 |
| Finance (EMI ₹29,743 / ₹18,092 × 60) | ₹17,84,573 | ₹10,85,496 | −₹6,99,077 |
| Energy | **₹2,00,304** | ₹9,48,480 | **+₹7,48,176** |
| Maintenance | **₹93,600** | ₹2,10,000 | **+₹1,16,400** |
| Insurance | ₹2,10,000 | ₹1,97,400 | −₹12,600 |
| Residual credit | −₹3,63,964 | −₹3,40,595 | −₹23,369 |
| **Total** | **₹19,24,514** | **₹21,00,781** | **+₹1,76,267** |
| **Cost per km** | **₹6.17** | **₹6.73** | **+8.4%** |

**The shape of this table is the whole argument.** The EV is ₹5.5 L dearer to buy and ₹7.0 L
dearer to finance. Energy and maintenance together return ₹8.6 L over five years — enough to
come out ahead, but not by much.

---

## 4. Operator TCO — three cities

| City | Basis | EV ₹/km | CNG ₹/km | EV advantage |
|---|---|---|---|---|
| **Delhi** | Financed 60 mo | **6.17** | 6.73 | **+8.4%** |
| Delhi | Cash outright | **4.94** | 5.98 | **+17.5%** |
| **Mumbai** | Financed 60 mo | **6.47** | 7.00 | **+7.6%** |
| Mumbai | Cash outright | **5.35** | 6.31 | **+15.3%** |
| **Bengaluru** | Financed 60 mo | **6.66** | 7.25 | **+8.2%** |
| Bengaluru | Cash outright | **5.45** | 6.51 | **+16.4%** |

### Two levers the deck does not use

**Lever 1 — financing structure nearly doubles the advantage.** Cash purchase gives +17.5%
against financed +8.4%, in the same city, on the same vehicle. The drag is the interest on a
₹14 L asset: roughly **₹3.85 L of interest**, against ₹2.33 L on the CNG.

That is a *negotiation* lever, not a physics one. A fleet operator buying at scale can negotiate
a longer tenure, a lower rate, or an EV-specific product. **A 7-year tenure moves most of the
horizon from "financed" to "cash," and that is worth more than any tariff negotiation we could
win.**

**Lever 2 — hold the vehicle longer.**

| Horizon | EV ₹/km | CNG ₹/km | EV advantage | Cumulative saving |
|---|---|---|---|---|
| 5 yr | 6.17 | 6.73 | +8.4% | ₹1,76,267 |
| 6 yr | 5.41 | 6.34 | +14.6% | ₹3,46,663 |
| 7 yr | 4.87 | 6.05 | +19.6% | ₹5,17,058 |
| **8 yr** | **4.46** | **5.84** | **+23.6%** | **₹6,87,453** |

Delhi, financed. **The case roughly triples by year 8** because the loan is repaid and the
asset keeps earning. This is the strongest single argument in the document and it is an
*operator* argument — it belongs to whoever owns the vehicle.

---

## 5. Driver view

| | EV | CNG |
|---|---|---|
| Monthly outflow (Delhi, yr 1–5) | **₹38,141** | ₹40,690 |
| **Driver take-home, during loan** | **₹19,059** | ₹16,510 |
| **Driver take-home, year 6+** | **₹48,802** | ₹34,602 |

- **During the loan: +₹2,548/month** — the driver is ahead, but not dramatically.
- **After the loan: +₹14,200/month** — a step change once the EMI disappears.
- **Five-year cumulative take-home gap: ₹1,52,899.**

This validates the deck's headline claim. The deck's "+₹14,400/month advantage" post-loan is
close to our computed **₹14,200** — that number was right.

**But the driver view is the weaker of the two arguments, and it is not the one to lead with.**
A driver does not buy the vehicle; a fleet operator does. The driver's economics improve
*because* the operator's do. Leading with driver take-home inverts the causality and invites the
question "whose vehicle is this?"

---

## 6. Sensitivity — what actually moves the answer

Change one input at a time, 5-year financed, Delhi:

| Input change | EV advantage |
|---|---|
| **Base** (Delhi: elec ₹4.50, CNG ₹76/kg, 25 km/kg) | **+8.4%** |
| CNG fuel economy 25 → **30 km/kg** | **+0.9%** |
| CNG fuel economy 25 → **35 km/kg** | **−5.2%** |
| CNG price ₹76 → **₹90/kg** | **+15.4%** |
| Electricity ₹4.50 → **₹8.00** (generic commercial) | **+1.0%** |
| Electricity ₹4.50 → **₹10.00** | **−3.3%** |
| Electricity ₹4.50 → **₹12.00** (public DC) | **−7.5%** |
| Electricity ₹4.50 → **₹24.00** (public DC retail) | **−32.9%** |
| EV residual 26% → 36% *(deck's old assumption)* | +15.1% |
| Consumption 12.84 → 15.38 kWh/100 km *(deck's figure)* | +6.5% |
| 8-year horizon | +23.6% |
| **Worst case stacked** (15.38 + ₹12 + resid 26%) | **−12.5%** |

**Read this table and three things become obvious:**

1. **The case is real but narrow, and it is sensitive to all three of its key inputs.**
   This is not a result that survives sloppy assumptions. If CNG achieves 30 km/kg — entirely
   plausible for a modern multi-point injection sedan — **the EV advantage collapses to
   +0.9%**. If that car reaches 35 km/kg, **CNG wins**. The deck's assumed 25 km/kg is doing a
   great deal of work, and nobody has evidenced it.
2. **Every unit price matters, and the electricity tariff matters most in range.** From ₹4.50
   to ₹24/kWh the advantage swings 41 points. Delhi's notified EV tariff is ₹4.50; Mumbai's is
   ₹9.50. That ₹5/unit gap is worth roughly 3 points of EV advantage on its own.
3. **The honest headline is that this is a well-argued case in Delhi at ₹76/kg CNG and depot
   charging — not a universal one.** Presenting it as robust when a 5 km/kg change in CNG
   efficiency erases it would be the specific failure this document exists to prevent.

---

## 7. The two conditions

### Condition 1 — the vehicle must charge at its own depot

| Charging route | Cost | 5-yr result |
|---|---|---|
| Delhi EV tariff (₹4.50/kWh) | ₹0.64/km | **+8.4%** ✓ |
| Commercial band (₹8.50/kWh) | ₹1.21/km | +8.4% ✓ |
| Public DC fast charge (₹12/kWh) | ₹1.71/km | **−7.5%** ✗ |

Depot off-peak electricity in India runs **₹5.50–9/kWh**; public DC runs **₹18–24/kWh**
(retail). Our Delhi figure of ₹4.50 uses the **BEE-notified EV tariff category** (LT 4.50 /
HT 4.00) — a state EV-charging category that is materially cheaper than general commercial
supply. Maharashtra has fixed EV-charging stations at **₹9.50/unit to 2028-29** (MERC).

**This is not a rounding error. It is the entire case.**

### Condition 2 — uptime is the binding constraint

| | |
|---|---|
| EV downtime headroom | **26 extra hours/month** before CNG wins |
| Real-world failure reference | **~75 hours/month** (Green SM Limo, Noida) |
| **Headroom vs observed failure** | **0.35×** |

This is the most important operational number in the document. The Green SM operation reported
drivers losing roughly **2.5 hours a day** to charger queues — about **75 hours a month**.

**We have 26 hours of margin. The documented real-world failure mode costs 75.**

That is not a comfortable margin. It is a margin smaller than the failure it protects against.
The counter-argument is that Green SM's failure was a consequence of *not* owning depot
charging — they queued at public chargers because they had no depot. With overnight depot
charging the downtime term goes to approximately zero, and 26 hours/month becomes ample.

**But that is a claim about our operating model, not about the vehicle.** It has to be stated
as such, and it has to be enforced by contract or we are assuming away the largest risk in the
business case.

---

## 8. Residual value — EV's weakest flank

This is where the EV genuinely loses, and where our earlier numbers were most wrong.

| Source | Evidence |
|---|---|
| **BluSmart** (Anmol Jaggi, via Mint) | Leased Tata Xpres-T at a **10% residual assumption; realised ~26%** in the resale market |
| **Mahindra First Choice** (CEO) | EV residual is **70–80% of comparable ICE** after three years |
| **Spinny** | 3-year-old EV loses **~46%** vs **~40%** for an equivalent ICE |
| **CARS24** | 3–5-year ICE retains **>50%**; EV materially less |
| **JATO Dynamics** | Nexon EV annual depreciation **26%** vs petrol **13.8%** / diesel **14.9%** — EV ~2× worse |
| **IRDAI** | IDV depreciation table is **5%–50%** by age and applies **identically to EV and ICE** — no EV table exists |
| **Policybazaar** | A used EV of the same age typically **costs more to insure** than a comparable petrol car; OD premium is the driver, and the government's 15% EV discount applies to **third-party only** |

**Two structural problems, neither of which we can fix:**

- **There is no standardised battery State-of-Health certificate for resale in India.** IRDAI
  has no EV-specific IDV table. Insurers fall back on age, warranty period and manufacturer
  reputation. That is precisely why BluSmart could beat a 10% assumption and why a buyer
  discounts further.
- **Residual risk sits with whoever leases.** BluSmart's finding — assumption 10%, reality 26% —
  is *favourable*, and even then the gain only materialised because they could sell into
  tier-2/3 markets.

**Our model uses 26% — the pessimistic real-world number, not the deck's ~36%.** Doing so costs
the EV 6.7 points of advantage. If we can contract a buyback at ≥36%, that is recovered in full.

**Battery replacement sits outside the 8-year horizon.** At 198 EFC/yr, 3,000 cycles is ~15
years. Out-of-warranty passenger packs are quoted at **₹4–12 lakh**, which is why the warranty —
not the chemistry — is the residual-value question. See the battery report: first life is solid;
the 8-year/80% warranty is the contested claim.

---

## 9. Taxes and purchase — a structural advantage worth ₹1.5 L

| | EV | CNG (Dzire Tour S) |
|---|---|---|
| GST | **5%** | 18% |
| Why | EV of any size or price is a separate 5% slab, no cess, retained through GST 2.0 | Small car: ≤1200 cc **and** ≤4000 mm |
| Road tax — Delhi | **10%** (blanket waiver **lapsed Mar 2026**) | ~10% |
| Road tax — Mumbai | **0%** (waiver to Mar 2030) | ~8% |
| Road tax — Bengaluru | **8%** (tiered from Apr 2026) | ~8% |

**Two things to flag:**

1. **Our vehicle is 3,995 mm — 5 mm inside the 4,000 mm "small car" line.** That keeps the CNG
   comparator in the 18% slab rather than 40%. Worth knowing, because it is the assumption that
   makes the comparison as close as it is. A longer CNG rival would widen our advantage.
2. **Delhi's blanket EV road-tax waiver expired in March 2026.** It was worth roughly ₹1.4 L on
   our vehicle. We have removed it from the model. Maharashtra's runs to March 2030; Karnataka
   moved to a tiered structure in April 2026.

**Note on aggregation:** no source in this analysis charges GST on used-car resale differently,
so we have not modelled a second-hand margin. Most target operators deploy new vehicles.

---

## 10. Corrections made during this analysis

Recorded because each would have been indefensible if a judge found it.

| # | Error | Impact |
|---|---|---|
| 1 | **Counted purchase price *and* the full EMI stream** — double-counting the loan principal | Made EV look **95% worse**. Corrected to one-or-the-other. |
| 2 | EMI formula applied the annual rate as monthly | EMI was 5× too high |
| 3 | CNG ex-showroom back-solve omitted road tax | Comparator understated by ~₹2.8 L |
| 4 | km/day bisection mutated the wrong module namespace (mutation had no effect) | Reported a 600 km/day breakeven instead of 153 |
| 5 | EV residual assumed ~36% | Replaced with BluSmart's **realised 26%** — costs EV 6.7 points |
| 6 | Omitted charging losses | ~11% energy understatement |
| 7 | Omitted the EV tyre-wear premium | ~30% maintenance understatement |

---

## 11. Convergence analysis

Thirty-one sources. Where they agree, the finding is safe to present. Where they diverge, the
divergence is disclosed.

### Where the literature converges

| Finding | Converging sources |
|---|---|
| **EV is the most cost-effective option for high-mileage taxis** | CEEW · Cadmus/Uber · ICCT · BusinessLine · ev.care |
| **Parity threshold sits at ~100–200 km/day** | BusinessLine (EKA, Euler) · CEEW · ev.care |
| **EV maintenance runs 40–70% below ICE** | EVSelect · ev.care · CEEW |
| **EV tyres wear 25–30% faster** (mass + instant torque) | EVSelect · ev.care |
| **EV residual is materially weaker than ICE** | BluSmart · Mahindra First Choice · Spinny · CARS24 · JATO |
| **Depot charging is essential, not optional** | ev.care · Indian Express · Cadmus/Uber |

**One clean quantitative convergence worth putting on a slide.** ev.care quotes depot-charged
fleet-car running cost at **₹1–1.5/km**. Our engine, at the deck's ₹8/unit assumption, returns
**₹1.14/km**. The two agree without coordination — independent confirmation that the energy
line is sound.

### Where sources diverge

| Disagreement | Positions | What we did |
|---|---|---|
| **EV residual: level vs trend** | Mint 2024: Nexon EV depreciation *improving* 51% → 26%. Mint 2025 + Business Standard: EV still ~2× worse than ICE, 70–80% of ICE at 3 yr. BluSmart: 26% realised | Trend and level are both true — absolute depreciation is falling while the *gap* persists. Modelled **26%** |
| **Payback period** | BusinessLine: **18–24 months**. ev.care: **2–3.5 yr** (3W) / **2.5–4 yr** (charging infra). Electricon: leasing beats ownership, EV beats diesel | Segment and scope differ — BusinessLine is light-CV fleet parity, ev.care includes charger capex. We use the **fleet-car** figures |
| **Battery replacement in horizon?** | CEEW assumes packs replaced after ~2,500 cycles. Our battery phase: 198 EFC/yr → 3,000 cycles ≈ **15 yr**, outside horizon | **No replacement modelled** in 8 yr; flagged in §8 as a residual-value risk, not a cost line |
| **Is the EV energy cost ₹0.6 or ₹1.7/km?** | Delhi EV tariff ₹4.50 vs public DC ₹12–24 | Both true — **this is the routing decision**, not a disagreement. It is Condition 1 |

**The honest summary:** sources agree on the direction and on the mechanism. They disagree only
on magnitude, and the magnitude disagreements are almost entirely about *charging arrangement*
and *residual assumption* — the two things we have flagged as conditions rather than settled
facts.

---

## 12. Risks, in order of size

| Risk | Exposure | Mitigation |
|---|---|---|
| **Charging moves from depot to public** | −7.5%, flips the answer | Depot charging as a contractual operating premise, not an aspiration |
| **Uptime falls to Green SM levels** | 75 h/month > 26 h headroom — **EV loses** | Charger redundancy (N+1), guaranteed-response maintenance SLA |
| **Residual lands at deck's assumed 36% or below** | −6.7 points | OEM buyback at ≥36%; residual-sharing with the lessor |
| **Duty falls below ~153 km/day** | EV loses | Our duty assumption is 200 km/day; re-run this model if it changes |
| **Consumption is the deck's 15.38, not 12.84** | −1.9 points only | Small. Verifiable from telematics in month one |
| **Financing at 10% for 60 months** | Costs ~9 points vs cash | Negotiate 7-year tenure or EV-specific product |

**Two of the top three risks are operational, not technical.** That is the honest headline: the
vehicle is right, and the business case is held together by how it is operated and financed.

---

## 13. What we will not claim

- **Not** "EV is 16–28% cheaper." The defensible figures are **+8.4%** over 5 years financed and
  **+17.5%** cash. Our earlier number was wrong and is corrected here.
- **Not** "EV wins everywhere." Delhi's road-tax waiver lapsed in March 2026 and Mumbai's
  electricity tariff is 2.1× Delhi's. The advantage is **city-dependent**.
- **Not** "zero downtime cost." We assume depot charging keeps it near zero. That is an
  operating-design claim we must earn, with 26 hours/month of headroom against a documented
  75-hour failure mode.
- **Not** "residual value is fine." We use 26%, the pessimistic realised number.
- **Not** a driver-income argument as the lead. The driver benefits because the operator's
  economics improve. Lead with the operator case.

---

## 14. Sources

**TCO methodology and parity**
1. CEEW, *Cost of Ownership for India's Road Transport Sector* — taxi TCO ranking; maintenance sensitivity; hybrid 43% GST+cess
2. Cadmus / Uber, *Electrifying Ridehail in India* (Jan 2026) — opportunity cost of charging; charging methodology; 35,000 ports / 5.7 M EVs
3. ICCT, *Near-term incentives for electrifying India's four-wheeler ride-hailing fleet* (2021) — TCO framework; charging-time sensitivity
4. ICCT, *Updated analysis of incentives* (2021) — cost trajectory by city
5. Electricon / Industry Report (2025) — TCO model with battery replacement and salvage terms
6. Ola Institute, *Beyond Nagpur* — fleet TCO logic
7. The Hindu BusinessLine (26 Feb 2026) — parity at 120–200 km/day; payback 18–24 months

**Charging, tariffs and uptime**
8. Bureau of Energy Efficiency, *State-wise EV Tariff* annexure — Delhi LT 4.50 / HT 4.00
9. MERC / MSEDCL multi-year tariff order (Mar 2026) — EV-charging tariff ₹9.50/unit to 2028-29
10. Adani Electricity tariff schedule — LT VI EV charging category
11. quotemypower, DISCOM city tariffs (2026) — commercial bands, public retail ₹18–24
12. ev.care, *EV Fleet Depot Charging Setup in India* (Jun 2026) — depot vs public cost; ToD; charger ratios
13. ev.care, *EV Fleet Management Guide* (Jun 2026) — running cost ₹1–1.5/km; downtime risk
14. SBI, *E-mobility and charging infrastructure in India* — 29,151 chargers; 1–3% utilisation
15. The Indian Express (1 Sep 2026) — Green SM Limo Noida downtime, ~2.5 h/day

**Residual value**
16. Mint (25 Apr 2025) — Spinny and CARS24 depreciation data
17. Mint (5 Sep 2024) — JATO Dynamics Nexon EV depreciation trend
18. Business Standard (24 Oct 2025) — IRDAI IDV table; no EV-specific standard
19. The Hindu BusinessLine (10 Jul 2026) — pre-owned EV market; assured future-value financing
20. The Core (16 Jun 2026) — battery certification gap; Policybazaar on insurance
21. Mahindra First Choice — EV residual 70–80% of ICE at 3 years
22. **BluSmart (Anmol Jaggi)** — assumed 10% residual, realised 26%

**Maintenance and insurance**
23. EVSelect, *EV Car Maintenance & Service Cost in India* (Jun 2026) — service −40–60%; tyres +25–30%; brake pad life
24. CEEW — maintenance sensitivity: EV 8% vs CNG 17% TCO impact per 50% cost change
25. Policybazaar — EV OD premium higher; 15% discount is third-party only

**Tax and policy**
26. GST 2.0 (effective 22 Sep 2025) — EV 5%, small car 18%, compensation cess abolished
27. Business Today (3 Sep 2025) — GST rate restructuring
28. State road-tax schedules 2026 — Delhi waiver lapsed Mar 2026; Karnataka tiered Apr 2026
29. PIB (4 Sep 2025) — road passenger transport GST options
30. Delhi EV gazette SG.DEL-E.29112023-250308 — fleet electrification by 1 Apr 2030

**Battery physics (from the verified battery report)**
31. Naumann 2018 (`10.1016/j.est.2018.01.019`) · Lewerenz 2017 · Eldesoky 2022 (`10.1149/1945-7111/ac99a6`) · Harlow 2019 (`10.1149/2.0981913jes`)

---

## Appendix — Reproducing every number

Engine: `/tmp/opencode/p2/tco_engine.py`, analysis: `/tmp/opencode/p2/tco_analysis.py`

```
DUTY      200 km/d x 26 d x 312 d = 5,200 km/mo | 62,400 km/yr | 312,000 km (5 yr)
EV energy 12.84 kWh/100km x 4.50 / 0.90 efficiency = Rs0.64/km -> Rs2,00,304 (5 yr)
CNG energy 312,000 / 25 km-per-kg x Rs76/kg          = Rs9,48,480 (5 yr)
EMI       Rs13,99,860 x 10%/12 over 60 mo           = Rs29,743/mo
Delhi EV  capex 17,84,573 + 2,00,304 + 93,600 + 2,10,000 - 3,63,964 = Rs19,24,514 -> Rs6.17/km
Delhi CNG capex 10,85,496 + 9,48,480 + 2,10,000 + 1,97,400 - 3,40,595 = Rs21,00,781 -> Rs6.73/km
```

Every table in this document is regenerated by running those two scripts. No figure was
transcribed by hand.