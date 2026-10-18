# MACH1 / FleetLine E1 — Market Evidence Slides (Rebuilt)

Companion to `MACH1_MARKET_ASSESSMENT.md`. Keep the scenario labels visible wherever figures are used.

---

## Slide 1 — Size the opportunity from observed rides

**Headline:** 591M annualized rides across three reported platforms; the E1 target pool is not yet directly measured.

### Build

| Reported daily platform rides | Daily rides | Source basis |
|---|---:|---|
| Uber | 840,000 | Motilal Oswal figure cited by Business Standard, Apr 2025 |
| Ola | 460,000 | Same source |
| Rapido | 320,000 | Same source; vehicle-class scope needs confirmation |
| **Combined** | **1.62M** | Sum of reported figures |
| **Annualized** | **591.3M** | ×365; constant run-rate conversion |

### Formula / transparent scenarios

`Annual ride GMV = 591.3M rides × target-segment share × average realized target fare`

| Scenario | Target share | Fare assumption | Illustrative annual GMV |
|---|---:|---:|---:|
| Low | 5% | ₹300 | **₹887 crore** |
| Central arithmetic case | 10% | ₹450 | **₹2,661 crore** |
| High | 15% | ₹600 | **₹5,322 crore** |

**Footnote:** Scenario envelope, not an observed TAM or forecast. The daily ride figures are a press-cited analyst estimate; ₹300 is a broad all-cab reference, and share/fare bounds are assumptions. The target use cases overlap, so do not sum without trip-level de-duplication.

**Speaker note:** “We can show the arithmetic and the uncertainty. The next research step is to replace the target-share and target-fare assumptions with city/operator trip evidence.”

---

## Slide 2 — What current evidence can answer

**Headline:** Registrations tell us what vehicles enter the market; trips tell us what fleets need.

| Evidence source | Answers | Does not answer |
|---|---|---|
| VAHAN / Autiqa Lens Pro | State, OEM, model, fuel, registration trends; seasonal mix; competitive share | Taxi-purpose share, fares, active fleet, paid km, driver/operator margin |
| AutoPunditz wholesale data | OEM/model dispatch trends, launches, powertrain competition | Retail registrations or taxi purchases without reconciliation |
| Platform/operator trips | Use case, fare, utilization, deadhead, cancellations, city demand | National market unless coverage is weighted and expanded |
| Rider MaxDiff/conjoint | Attribute trade-offs and preference segments | Actual fleet economics or vehicle purchase conversion |

### Research choices

- **Forecast registrations:** seasonal-naive baseline vs ETS/Holt–Winters, rolling backtest; report error and scope.
- **Estimate EV adoption effects:** city/state monthly panel; fixed effects or DiD only when policy exposure, comparison groups, and pre-trends are credible.
- **Group demand types:** observed city × use-case cells, exploratory hierarchical clustering with scaling/linkage/resampling checks.
- **Choose vehicle configuration:** evidence-backed weighted decision matrix; show weight sensitivity.

**Speaker note:** “We do not have a sample for segmentation or regression yet. We are separating supply-side data from demand-side data before making a causal or product-fit claim.”

---

## Slide 3 — The decision still to validate

**Headline:** Test where E1 economics work before calling a segment the winner.

### Required operator evidence

1. Paid and total km per shift, including empty return/deadhead.
2. Completed trips, fare distribution, trip purpose, booking channel, and city.
3. Energy/fuel, maintenance, charging/refuelling downtime, uptime, and airport fees.
4. Vehicle price/finance, insurance, warranty, taxes, residual value, and replacement cycle.
5. Contract terms: operator take, driver take, commission/subscription, minimum utilization.

### Vehicle-market evidence to pair with it

- Lens Pro / VAHAN: model, fuel, geography, and month registration panels, with consistent national denominators.
- AutoPunditz: monthly OEM/model wholesale panel; keep wholesale and retail series distinct.
- Fleet purchases / permits: identify active commercial vehicles and replacement rather than treating every registration as a taxi.

**Conclusion:** Airport, corporate, commute, city, premium, and intercity are overlapping dimensions. Until trip and operator data are obtained, E1’s target and duty-cycle fit remain hypotheses, not findings.
