# Total Cost of Ownership Analysis
### MACH1 / FleetLine E1 — operator and driver economics
### Built on 53 sources across 51 numbered entries, with an explicit convergence analysis
### **Revision 4 — re-audited after adversarial review. Economic boundary stated, depot
### charging infrastructure costed, cash flows discounted, revenue definition corrected.**

---

## 0. Headline

**The EV is cheaper in every case we modelled — but the margin is roughly half what we
claimed in Revision 3, and the five-year case does not close outside Delhi.**

| Finding | Rev 3 said | Rev 4 says |
|---|---|---|
| Delhi, 5 years | +14.5% | **+6.7%** |
| Delhi, 8 years | +28.0% | **+14.6%** |
| "Wins in every city modelled" | claimed | **withdrawn** — false on 4 of 48 cells |
| Cash purchase advantage | +22.6% | **does not survive discounting** |
| Driver take-home (during loan) | ₹21,763 | **₹20,021** (revenue was mis-stated) |
| Uptime headroom | 45 h/month | **21.9 h/month** beyond a non-zero baseline |

**All Rev 4 figures are on one basis: NPV at a 12% hurdle, escalated, financed 60 months,
*including* depot charging infrastructure.** That is the only basis that prices what the
operator actually faces. §4 explains why.

**The result in one sentence: the vehicle is right, and the business case is held together by
holding period, electricity tariff and charger cost — not by the vehicle.**

### Why the number fell

Almost none of this is new physics. It is one omission, and it was large:

- **Depot charging infrastructure was never costed at all.** A fleet operator buys a
  ₹99,000 charging port per vehicle. Revision 3 excluded it on the grounds that it sat
  outside a "vehicle-level" boundary — while simultaneously making depot charging the
  load-bearing condition of the entire business case. That is inconsistent. Counting it
  costs **9.3 percentage points** at five years.
- The remaining changes are smaller and mostly definitional: discounting, escalation,
  a corrected platform-fee structure, and a downtime baseline that is no longer zero.

**One genuine error, not an omission:** Revision 3's sensitivity table reported that a rise in
the *CNG* residual from 40% to 45% would lift the EV advantage to +26.0%. That cell was
reporting the *EV's* residual set to 45% — a routing bug in the analysis script. The correct
value is **+12.8%**. It was the one number in Revision 3 that was simply wrong rather than
incomplete. See §13.

---

## 1. Method and economic boundary

**The economic boundary is now stated explicitly, because the previous revision drew it in a
place that flattered the answer.**

Per the brief — *purchase, energy, maintenance, uptime, residual value* — from both the
operator's and the driver's view.

**Costed once, never twice.** Capital cost appears either as the cash on-road price *or* as
the full EMI stream, never both. An early draft added both, double-counting the loan
principal and making the EV look 95% worse.

### Included in the boundary

| Included | Detail |
|---|---|
| Acquisition | Ex-showroom, GST, road tax (per vehicle) |
| Financing | Full EMI stream, 10% / 60 months |
| Energy | Tariff × consumption, net of charging losses |
| Maintenance | Fleet service cost, net of the EV tyre-wear premium |
| Insurance | OD premium, actual, EV higher than CNG |
| **Charging infrastructure** | **NEW — charger capex, installation, DISCOM load sanction, N+1 redundancy, management software, AMC, and replacement at year 5** |
| Downtime | Foregone **net** earnings, decomposed by cause (§9) |
| Residual | Credit at end of horizon, escalated |
| CNG-side infra | Periodic cylinder hydro-testing |

### Excluded, with reason

| Excluded | Why |
|---|---|
| Aggregator platform fee | **A flat ₹67 per vehicle-day, identical for both vehicles, so it cancels.** It is not a percentage of fare and is applied to neither vehicle preferentially. §7 shows the EV−CNG delta is invariant to it. |
| Toll / FASTag | Vehicle-class dependent, not powertrain dependent |
| Driver salary as a cost | Treated on the revenue side; only *lost* earning time is costed |
| Public DC charging energy | Modelled as a sensitivity (§9), not the base case |
| Depot land and lease | The depot exists whether or not the vehicle does; and if it did not exist, neither vehicle could operate |
| Electricity **demand charges** | DISCOM-contract dependent. Disclosed as a sensitivity in §9 — they bite above 50 kW connected load, which a real depot crosses |
| Financing fees / arrangement fees | Not separately quoted; would apply to both |

---

## 2. Configuration

| | |
|---|---|
| **Vehicle** | FleetLine E1 — BEV, LFP 45 kWh, PMSM 80 bhp continuous, single-speed |
| **Comparator** | Maruti Dzire Tour S (CNG) — factory CNG kit, so no per-vehicle retrofit |
| **Duty** | 200 km/day × 26 days × 312 days = **5,200 km/mo · 62,400 km/yr** |
| **Consumption** | **12.84 kWh/100 km** battery-side (corrects the deck's 15.38) |
| **Charging** | Depot AC overnight, **90% wall-to-battery** |
| **Gross fare** | ₹11/km → ₹57,200/month |
| **Platform fee** | ₹67/vehicle-day (Ola zero-commission) → ₹1,742/month |
| **Net fare to driver** | **₹10.665/km → ₹55,458/month** (derived, §7) |
| **Financing** | 10% annual, 60 months, no down payment |
| **Horizons** | 5 years (loan) and 8 years (battery phase) |
| **Discount rate** | **12% nominal annual** — a fleet operator's hurdle rate |
| **Escalation** | Electricity 4.5% · CNG 3.5% · maintenance 4.0% · insurance 5.0% · residual 4.5% |
| **Cities** | Delhi, Mumbai, Bengaluru |

Escalation rates are sourced, not assumed: CERC's notified domestic-gas escalation is
**3.46%/yr**; PNGRB's APM trajectory (+$0.25/financial year) independently gives 3.47%. CEA
tariff data for 2014–24 puts LT commercial CAGR at **5.1%/yr**. We use 4.5% for electricity as
a deliberately conservative discount to that, and we disclose the counter-case: Maharashtra's
2026 multi-year order **cuts** tariffs annually through 2030.

---

## 3. The cost stack — Delhi, 5 years, financed

| Component | EV | CNG | EV advantage |
|---|---|---|---|
| On-road (ex-showroom + GST + road tax) | ₹12,72,600 | ₹8,51,488 | −₹4,21,112 |
| Finance (EMI ₹27,039 / ₹18,092 × 60) | ₹16,22,339 | ₹10,85,496 | −₹5,36,843 |
| Energy | **₹2,00,304** | ₹9,48,480 | **+₹7,48,176** |
| Maintenance | **₹93,600** | ₹2,10,000 | **+₹1,16,400** |
| Insurance | ₹2,10,000 | ₹1,97,400 | −₹12,600 |
| Residual credit | −₹3,30,876 | −₹3,40,595 | +₹9,719 |
| **Subtotal — vehicle only** | **₹17,95,367** | **₹21,00,781** | **+₹3,05,414** |
| **Charging infrastructure** | **₹1,74,000** | ₹4,500 | **−₹1,69,500** |
| **Total, boundary-complete** | **₹19,69,367** | **₹21,05,281** | **+₹1,35,914** |
| **Cost per km** | **₹6.31** | **₹6.75** | **+6.5%** |

**The shape of this table is still the argument.** The EV is ₹4.2 L dearer to buy and ₹5.4 L
dearer to finance. Energy and maintenance return **₹8.6 L** over five years — more than the
₹9.6 L premium — leaving ₹3.05 L. A ₹99,000 charger per vehicle takes ₹1.70 L of that.

Infrastructure per kilometre: **EV ₹0.558 · CNG ₹0.014**. That asymmetry is the whole
revision. It is not an accounting artefact — the CNG vehicle's kit is already inside its
ex-showroom price, and it needs only periodic cylinder hydro-testing.

Note the residual line: **the CNG comparator recovers slightly more** (₹3.41 L vs ₹3.31 L),
because 40% of a cheaper car is close to 26% of a dearer one.

### NPV component view — the same case, Delhi, 5 years, financed, 12% hurdle

| Component (₹ NPV) | EV | CNG |
|---|---|---|
| Finance | 12,15,539 | 8,13,309 |
| Energy | 1,62,496 | 7,55,955 |
| Maintenance | 75,264 | 1,68,861 |
| Insurance | 1,71,876 | 1,61,563 |
| Residual credit | −2,17,194 | −2,23,574 |
| **Charging infrastructure** | **1,59,307** | 3,145 |
| **Total NPV** | **15,67,287** | **16,79,260** |
| **Advantage** | | **+6.7%** |

Escalation *raises* the advantage (+14.1% → +16.0% before infrastructure). Electricity rises
at 4.5% and CNG at 3.5%, but CNG's energy bill is 4.7× larger in absolute rupees, so it grows
faster in cash terms despite the lower rate. **The entire downward movement in this document
is the charger. None of it is energy-price risk.**

---

## 4. Choosing one basis

The same vehicle produces these answers, all arithmetically correct:

| Basis | 5 years | 8 years |
|---|---|---|
| Nominal, excluding infrastructure | +14.5% | +28.0% |
| Nominal, **including** infrastructure | +6.5% | +17.4% |
| NPV 12% escalated, excluding infrastructure | +16.0% | +25.3% |
| **NPV 12% escalated, including infrastructure** | **+6.7%** | **+14.6%** |

**We quote the bottom row, and only that row, as the result.** Three reasons:

1. **A 12% hurdle prices the deferred capital.** The difference between cash and financed is
   a financing decision, not a property of the vehicle. Presenting both as though they were
   two views of one fact — as Revision 3 did — is the error the reviewer identified. On a
   12% basis the answer is one number.
2. **Escalation prices the price trajectory** rather than assuming 2026 prices hold for eight
   years.
3. **Infrastructure prices a cost only the EV has.** Quoting a figure that omits it is not a
   different boundary — it is an incorrect one, because the document simultaneously relies on
   depot charging as the condition that makes the case work.

**Revision 3's +22.6% cash figure does not survive this.** At a 12% hurdle, cash purchase and
financing converge to roughly the same economic cost, because a 10% loan discounted at a 12%
hurdle is genuinely value-accretive. In *nominal cash terms* cash still looks better — you
avoid ₹3,49,739 of interest — but that is borrowing cost, not a cheaper vehicle. **We no longer
quote the +22.6% as an advantage.**

---

## 5. The city matrix — where the case closes, and where it does not

The ₹99,000 port is **city-independent**. What changes by city is the electricity tariff, the
road tax and the CNG price. So infrastructure is a flat EV-side charge set against a
city-specific energy saving — which is precisely why the ranking moves.

**48 cells = 3 cities × 2 horizons × 2 capital structures × 4 bases.**

> ### 4 of 48 cells are negative.
> All four are at **five years**. All four are **infrastructure-inclusive**.
> Excluding the charger, all 44 remaining cells are positive and no city fails.

**NPV @ 12% escalated, including infrastructure — the headline basis**

| | 5-yr financed | 5-yr cash | 8-yr financed | 8-yr cash |
|---|---|---|---|---|
| **Delhi** | **+6.7%** | **+5.4%** | **+14.6%** | **+13.5%** |
| **Mumbai** | **−0.2%** | **−1.4%** | **+7.5%** | **+6.4%** |
| **Bengaluru** | **+0.9%** | **−0.4%** | **+9.0%** | **+7.9%** |

### What this means, plainly

**Delhi clears at five years on every basis.** +5.4% to +22.6% depending on how you frame it,
and ₹1,11,972 of headroom on charger cost — the port could cost twice what we assumed.

**Mumbai does not clear at five years.** Three of four cells are negative. Its breakeven
charger cost is **₹96,171 — below the ₹99,000 we assumed**. Mumbai is already past break-even
by ₹2,829. It needs a cheaper port, not better financing.

**Bengaluru is marginal.** +0.9% financed, −0.4% on NPV cash, and only ₹16,197 of charger
headroom — 16% of the charger budget. A pass on arithmetic, not a comfortable pass.

**Every eight-year cell is positive, in every city, on every basis** — the weakest is Mumbai
cash NPV at +6.4%.

### The duty requirement rises once infrastructure is counted

| City | Horizon | Breakeven duty, no infra | **with infra** | vs the deck's 200 km/day |
|---|---|---|---|---|
| Delhi | 5 yr | 118.4 | **162.3** | 1.23× |
| **Mumbai** | **5 yr** | 151.2 | **201.1** | **0.99× — fails** |
| Bengaluru | 5 yr | 150.3 | **194.5** | 1.03× |
| Delhi | 8 yr | 63.6 | **124.0** | 1.61× |
| Mumbai | 8 yr | 83.0 | **154.2** | 1.30× |
| Bengaluru | 8 yr | 83.5 | **148.3** | 1.35× |

**Mumbai's five-year breakeven is 201.1 km/day — one km above the 200 km/day the proposal
itself assumes.** On the deck's own numbers, a five-year Mumbai fleet does not close. Not
"is marginal" — does not clear. That is a fleet-design question, not a vehicle question, and it
is the thing most likely to be pushed back on.

> **What we would write on a slide:** *The EV wins in Delhi on any basis at any horizon.
> Outside Delhi it wins on holding period, not on purchase terms — at eight years every city is
> positive on every basis; at five years no city except Delhi clears its own assumed duty once
> the charger is counted.*

> **What we will not write:** *"finance it cheaply enough."* That lever does not exist outside
> Delhi at five years. Note the counter-intuitive part — on the NPV basis **financing helps
> the EV**, because a 10% loan discounted at a 12% hurdle is cheaper than cash and the EV is
> the capital-intensive side (₹12.73 L on-road versus ₹7.74 L in Mumbai). That benefit is worth
> roughly ₹21,600 in Mumbai and the EV is *still* negative after it. Cheap credit is not the
> problem.

---

## 6. Operator economics — horizon and capital structure

**Nominal, excluding infrastructure** (the Revision 3 comparison, for continuity):

| City | Basis | EV ₹/km | CNG ₹/km | Advantage |
|---|---|---|---|---|
| **Delhi** | Financed 60 mo | **5.75** | 6.73 | **+14.5%** |
| Delhi | Cash outright | 4.63 | 5.98 | +22.6% |
| **Mumbai** | Financed 60 mo | 6.47 | 7.00 | **+7.6%** |
| Mumbai | Cash outright | 5.35 | 6.31 | +15.3% |
| **Bengaluru** | Financed 60 mo | 6.66 | 7.25 | **+8.2%** |
| Bengaluru | Cash outright | 5.45 | 6.51 | +16.4% |

Delhi is strongest because it combines **both** a ₹4.50/kWh EV tariff *and* a full road-tax
exemption on the EV while the CNG comparator pays standard tax. Mumbai's ₹9.50 tariff costs it
seven points.

### Holding period — the strongest single argument in the document

| Horizon | EV ₹/km | CNG ₹/km | Advantage, no infra | **with infra** | **NPV + infra** |
|---|---|---|---|---|---|
| 5 yr | 5.75 | 6.73 | +14.5% | **+6.5%** | **+6.7%** |
| 6 yr | 5.06 | 6.34 | +20.1% | — | — |
| 7 yr | 4.57 | 6.05 | +24.4% | — | — |
| **8 yr** | 4.20 | 5.84 | +28.0% | **+17.4%** | **+14.6%** |

The case roughly doubles between year 5 and year 8 because the loan is repaid and the asset
keeps earning. This is an *operator* argument — it belongs to whoever owns the vehicle, which
is the basis on which the whole document is framed.

### Price headroom

The EV's on-road price could rise to **₹15,73,553** before the case fails — **₹3,00,953, or
23.6%**, of headroom. The vehicle is not expensive enough to be the problem.

---

## 7. Driver economics — corrected revenue definition, two ownership models

### The correction

Revision 3 described ₹11/km as a "net fare" in one place and ₹57,200/month as "gross revenue"
in another, and excluded a "20–25% aggregator commission" that no longer exists. All three
statements could not be true at once. Here is the resolution:

- **₹11/km is gross fare** — what the rider pays.
- **The platform fee is now flat, not proportional.** Ola moved to zero-commission pan-India in
  June 2025 at **₹67 per vehicle-day**, replacing per-ride commissions of 15–30%. Uber and
  Rapido use subscription passes on the same model.
- **Net fare to the driver is therefore ₹10.665/km** (₹57,200 − ₹1,742 over 5,200 km) =
  **₹55,458/month**.

This cross-checks well against Redseer data cited by the Times of India: eight trips/day at
₹300 average gives ~₹60,000/month gross, ~₹58,325 net under the ₹67/day fee. Our ₹55,458 is
in the same place.

**The flat fee is charged per vehicle-day, so it is identical for the EV and the CNG. It
therefore cancels in the comparison.** Verified numerically: substituting a legacy 25% per-ride
commission changes the driver's absolute income but moves the EV−CNG delta by **₹0**.

### Model A — driver-owned

| | EV | CNG |
|---|---|---|
| Monthly outflow (Delhi, yr 1–5) | **₹35,437** | ₹40,690 |
| Net revenue | ₹55,458 | ₹55,458 |
| **Driver take-home, during loan** | **₹20,021** | **₹14,768** |
| **Driver take-home, year 6+** | **₹47,060** | **₹32,860** |
| Advantage | **+₹5,252/mo** | **+₹14,200/mo** |

### Model B — fleet-owned

Under a fleet-owned or lease arrangement the driver carries no capital cost at all:

| | EV | CNG |
|---|---|---|
| Monthly outflow (energy + maint + ins) | ₹8,398 | ₹22,598 |
| **Driver take-home, all years** | **₹47,060** | **₹32,860** |
| Advantage | | **+₹14,200/mo** |

### Which model applies does not change the vehicle's economics

**The owner's five-year advantage is ₹3,05,414 under Model A and ₹3,05,414 under Model B — a
difference of ₹0.** Ownership decides only whose balance sheet carries the vehicle. An operator
buying the car and a driver buying the same car have the same net position over five years.

**What changes is the monthly line the driver sees** — ₹5,252 ahead during the loan, ₹14,200
ahead once it is gone — and that is a contract term, not a property of the powertrain.

> **A finding worth stating.** At ₹11/km gross, a *driver-owned* vehicle under the old 25%
> commission model **loses money** — net revenue ₹28,600 against ₹35,437 of outflow. The
> flat-fee shift is not a convenience; at this fare level it is what makes driver ownership
> viable at all. That is a point in favour of the current platform structure, and it applies
> equally to both powertrains.

**The driver view is the weaker of the two arguments and is not the one to lead with.** A driver
does not buy the vehicle; a fleet operator does. The driver's economics improve *because* the
operator's do.

---

## 8. Sensitivity

Change one input at a time. 5-year financed, Delhi, nominal, excluding infrastructure unless
stated — this preserves comparability with the corrected Revision 3 table.

| Input change | EV advantage |
|---|---|
| **Base** (elec ₹4.50, CNG ₹76/kg, 25 km/kg) | **+14.5%** |
| CNG 22 km/kg — *city only, AC on* | +19.5% |
| CNG 24 km/kg — *city-heavy, measured* | +16.1% |
| CNG 27 km/kg — *mixed, optimistic* | +11.6% |
| CNG 30 km/kg — *highway, not metro duty* | +7.6% |
| CNG price ₹76 → ₹90/kg | +21.1% |
| **CNG residual 40% → 45%** | **+12.8%** *(was wrongly reported as +26.0% — §13)* |
| EV residual 26% → 36% *(deck's old assumption)* | +20.6% |
| Consumption 12.84 → 15.38 kWh/100 km *(deck's)* | +12.7% |
| Electricity ₹4.50 → ₹8.00 | +7.1% |
| Electricity ₹4.50 → ₹8.50 | +6.1% |
| Electricity ₹4.50 → ₹10.00 | +2.9% |
| Electricity ₹4.50 → **₹12.00** (public DC) | **−1.4%** ✗ |
| Electricity ₹4.50 → ₹18.00 | −14.1% ✗ |
| **Worst case stacked** (15.38 + ₹12 + resid 26%) | **−6.4%** |
| **Best case stacked** (12.84 + ₹4.50 + resid 36%) | **+20.6%** |
| 8-year horizon | +28.0% |

### On the stated boundary — the sensitivities that actually matter

| Change | Delhi 5-yr | Mumbai 5-yr | Bengaluru 5-yr |
|---|---|---|---|
| **Base, NPV + infra** | **+6.7%** | **−0.2%** | **+0.9%** |
| Charger at ₹60,000 | +9.0% | +2.1% | +3.1% |
| Charger at ₹1,50,000 | +3.6% | −3.1% | −1.9% |
| Demand charge ₹500/veh/mo | +5.0% | — | — |
| Demand charge ₹1,000/veh/mo | +3.6% | — | — |
| Duty 250 km/day | — | clears | clears |

**Solved breakeven charger cost, 5-year financed, NPV basis:**

| City | Breakeven charger | vs our ₹99,000 assumption |
|---|---|---|
| Delhi | ₹2,10,972 | ₹1,11,972 of headroom |
| Bengaluru | ₹1,15,197 | ₹16,197 of headroom |
| **Mumbai** | **₹96,171** | **loses by ₹2,829** |

**The charger is the single most important controllable number in this document.**

### Demand charges

Delhi's BEE-notified EV tariff category (LT 4.50 / HT 4.00) is energy-only, so demand charges
are zero in our base case. Real depots exceed 50 kW connected load, where fixed monthly demand
charges apply. If a depot's contract carries ₹500–1,000 per vehicle-month, the Delhi five-year
advantage falls from +6.5% to **+5.0% / +3.6%**. This is a contract term to be negotiated, not
a vehicle property.

### The CNG fuel-economy band is measured, not assumed

| Condition | Dzire CNG real-world | Source |
|---|---|---|
| **City, AC on** | **22.0 – 25.0** | cars24 (2026); buyselltaxi (2026, Delhi operators) |
| **Mixed, typical Ola/Uber pattern** | **24.0 – 27.0** | buyselltaxi (2026) |
| Highway / outstation | 28.0 – 32.0 | both |
| Swift CNG road test — city loop | 21.28 | CarTrade (2025) |
| Swift CNG road test — highway loop | 35.01 | CarTrade (2025) |
| ARAI claimed | 33.7 – 34.3 | — |

**For 200 km/day metro duty with AC on, the defensible band is 22–27 km/kg and the proposal's
25 sits in the middle.** The EV wins across all of it — and still wins at 35 km/kg, a
highway-grade figure this duty never sees. **Present the band, not a single number.** An
industry judge who knows the real figure will respect that you already priced it in.

**Convergence check:** buyselltaxi independently computes Delhi CNG at **₹3.19/km**; our engine
returns **₹3.17/km** at the same 24 km/kg — two unrelated sources agreeing to within 0.7% on
the largest line in the comparison.

---

## 9. The conditions

### Condition 1 — the vehicle must charge at its own depot

| Charging route | Energy cost | 5-yr result, no infra | **with infra** |
|---|---|---|---|
| **Delhi EV tariff (₹4.50/kWh)** | ₹0.64/km | **+14.5%** | **+6.5%** |
| Delhi commercial band (₹8.50/kWh) | ₹1.21/km | +6.1% | — |
| Public DC fast charge (₹12/kWh) | ₹1.71/km | −1.4% ✗ | ✗ |

Depot off-peak electricity in India runs **₹5.50–9/kWh**; public DC retail runs **₹18–24/kWh**.

**But depot charging is no longer free.** It requires capital:

| Item | Per vehicle | Source basis |
|---|---|---|
| 7.4 kW AC port, hardware | ₹50,000 | Commercial AC range ₹35k–75k; installed ₹50k–1.25L |
| Installation (cabling, MCB/RCCB, earthing, civil) | ₹30,000 | Commercial per-charger ₹20k–50k excl. civil |
| DISCOM load sanction / deposit | ₹10,000 | ₹5k–10k load increase on a single-car charger |
| **Subtotal** | ₹90,000 | |
| N+1 redundancy (1 spare per 10 vehicles) | ×1.1 | |
| **Charger capex** | **₹99,000** | |
| Management software / OCPP | ₹12,000/yr | ₹500–1,000 per port per month |
| AMC | ₹3,000/yr | ~3% of hardware |
| **Annual opex** | **₹15,000** | |

**Port sizing is not a guess.** Nightly energy is 200 km × 12.84 kWh/100 = **25.68 kWh**. At
7.4 kW that is **3.86 hours** — comfortably inside an overnight window, so **one port per
vehicle** is sufficient and a DC fast charger, at ₹4–12 lakh, is not required at all. ev.care
independently makes the same point: AC slow charging is "cheapest per port and ideal for
overnight charging when vehicles park for 8 to 12 hours."

Depots commonly also need load-balancing across sockets to avoid tripping a feeder, and a
real depot will cross 50 kW connected load, bringing demand charges into play (§8).

**This is the binding condition, and it is now a two-part condition: not just "have depot
charging" but "have depot charging, and amortise a ₹99,000 port per vehicle over five years."**

### Condition 2 — uptime

The previous revision reported "45 hours/month of headroom." That was a **breakeven
threshold**, presented as though it were slack. It is now decomposed against a stated baseline.

**Base-case downtime: 3.5 hours/month.** Not zero — depot charging reduces downtime, it does not
eliminate it.

| Cause | Hours/month |
|---|---|
| Charging queue / port unavailable | 0.5 |
| Planned maintenance | 1.0 |
| Unplanned repair | 1.5 |
| Charger failure awaiting spare | 0.5 |
| **Total base case** | **3.5** |

**Economic cost of a lost hour is derived, not assumed:**

| Component | ₹/hour |
|---|---|
| Gross foregone revenue (20 productive km × ₹11) | 220.00 |
| less platform fee (20 km × ₹0.335/km) | −6.70 |
| less energy avoided (20 km × ₹0.642/km) | −12.84 |
| **Net cost per lost hour** | **₹200.46** |

| | |
|---|---|
| Base-case downtime cost | ₹702/month · ₹0.135/km · ₹42,097 over 5 years |
| **Breakeven** | **25.4 h/month total = 21.9 h/month beyond the 3.5 h baseline** |
| At Green SM Limo's documented ~75 h/month | **−28.4%** |

**The real number is 21.9 hours, not 45.** The previous figure was the same economics expressed
against a zero baseline; both are arithmetically consistent, but only one of them tells an
operator how much room they actually have.

Green SM drivers in Noida reported losing ~2.5 hours a day to charger queues — about 75 hours a
month. The counter-argument stands and is important: **that loss was a consequence of not owning
depot charging.** With contracted overnight depot charging the base case is 3.5 hours. **But that
is a claim about our operating model, not about the vehicle**, and it must be written into the
contract or we are assuming away the largest operational risk in the business case.

---

## 10. Residual value — the EV's weakest flank

| Source | Evidence |
|---|---|
| **BluSmart** (Anmol Jaggi, via Mint) | Leased Tata Xpres-T at a **10% residual assumption; realised ~26%** |
| **Mahindra First Choice** (CEO) | EV residual is **70–80% of comparable ICE** after three years |
| **Spinny** | 3-year-old EV loses **~46%** vs **~40%** for an equivalent ICE |
| **CARS24** | 3–5-year ICE retains **>50%**; EV materially less |
| **JATO Dynamics** | Nexon EV annual depreciation **26%** vs petrol **13.8%** / diesel **14.9%** |
| **IRDAI** | IDV depreciation **5%–50%** by age, applied **identically to EV and ICE** — no EV table |
| **Policybazaar** | A used EV of the same age typically **costs more to insure** |

**Two structural problems, neither of which we can fix:**

- **No standardised battery State-of-Health certificate for resale in India.** Insurers fall back
  on age, warranty and manufacturer reputation. That is precisely why BluSmart beat a 10%
  assumption — and why other buyers discount further.
- **Residual risk sits with whoever leases.** BluSmart's 10%-assumed, 26%-realised finding is
  *favourable*, and even then only because they could sell into tier-2/3 markets.

**We model 26% — the pessimistic realised number.** That costs the EV 6.1 points. A buyback
contracted at ≥36% recovers it in full.

---

## 11. Taxes and purchase

| | EV | CNG (Dzire Tour S) |
|---|---|---|
| GST | **5%** | 18% |
| Road tax — Delhi | **0%** — full exemption for the **life of the vehicle** | ~10% |
| Road tax — Mumbai | 0% (waiver to Mar 2030) | ~8% |
| Road tax — Bengaluru | 8% (tiered from Apr 2026) | ~8% |

**Delhi Electric Vehicles Policy 2026** was approved by the Council of Ministers on 29 June 2026,
notified 30 June, effective 1 July 2026, running to 31 March 2030: **100% exemption from road
tax and registration fees** for EVs registered in the period, **throughout the life of the
vehicle**. For electric cars the exemption applies where ex-showroom ≤ ₹30 lakh — ours is
₹12.12 L, so it qualifies. Worth **₹1,27,260**.

> **Correction to a correction.** An earlier revision removed Delhi's EV road-tax waiver entirely,
> on the strength of a secondary compilation citing the *draft* policy and reporting a March 2026
> lapse. That was wrong — the policy lapsed and was then re-enacted. The error *penalised* the
> EV by ₹1,27,260. **Lesson: a policy change must be verified against the notified instrument,
> not a summary table.**

**Two other things to flag:**

1. **Our vehicle is 3,995 mm — 5 mm inside the 4,000 mm "small car" line.** That keeps the CNG
   comparator in the 18% slab rather than 40%. It is the assumption that makes the comparison as
   close as it is; a longer CNG rival would widen our advantage.
2. **Karnataka moved to tiered EV taxation in April 2026** (5% up to ₹10 L, 8% ₹10–25 L, 10%
   above), so Bengaluru no longer offers a blanket waiver.

---

## 12. Battery — replacement risk and the EFC definition

### The risk

Our model assumes **no pack replacement within eight years**. If one occurs, it dominates
everything else in this document:

| Replacement cost | EV ₹/km | EV advantage |
|---|---|---|
| No replacement (modelled) | 5.75 | +14.5% |
| ₹4 L pack | 7.04 | −4.5% |
| ₹8 L pack | 8.32 | −23.5% |
| ₹12 L pack | 9.60 | −42.6% |

**Even a ₹4 L pack at ₹3,500/kWh reverses the entire case.** Whether it happens depends on the
calendar exponent the battery phase found contested: Naumann's √t law gives **13.3 years** to
80% at 40 °C; Lewerenz's measured linear law gives **3.7 years**. At the duty modelled here the
pessimistic case reaches 80% around year four.

**So the warranty structure, not the chemistry, carries this risk.** Mitigation is contractual:
a capacity-retention guarantee or pack-to-pack service.

### The EFC definition, stated explicitly

The previous revision cited ~198 equivalent full cycles per year. That figure is reproducible,
but it depends on a choice that was never stated:

| Basis | EFC/yr | Time to 3,000 cycles |
|---|---|---|
| Battery-side throughput ÷ **nominal 45 kWh** | **178.0** | **16.85 yr** |
| Battery-side throughput ÷ **usable 44.2 kWh** | **181.3** | 16.55 yr |
| **Wall energy ÷ nominal 45 kWh** ← the published basis | **197.8** | **15.16 yr** |

Battery-side throughput is 12.84 kWh/100 km × 62,400 km = **8,012 kWh/year**.

**The published 197.8 mixes wall energy — which includes charging losses — with nominal
capacity, and overstates EFC by 11.1%.** On a consistent basis it is 178 EFC/yr, and time to
3,000 cycles is 16.9 years rather than 15.2.

**We have not changed the battery report.** Its figures stand as published; this section exists
so that anyone re-deriving them knows which definition produces them. The correction makes the
battery case slightly *better*, not worse.

---

## 13. Corrections

Recorded because each would have been indefensible if a judge found it.

| # | Error | Impact |
|---|---|---|
| 1 | Counted purchase price *and* the full EMI stream — double-counting principal | Made EV look **95% worse** |
| 2 | EMI formula applied the annual rate as monthly | EMI 5× too high |
| 3 | CNG ex-showroom back-solve omitted road tax | Comparator understated ~₹2.8 L |
| 4 | km/day bisection mutated the wrong module namespace | Reported 600 km/day breakeven instead of 153 |
| 5 | EV residual assumed ~36% | Replaced with BluSmart's **realised 26%** |
| 6 | Omitted charging losses | ~11% energy understatement |
| 7 | Omitted the EV tyre-wear premium | ~30% maintenance understatement |
| 8 | Overstated the advantage as "16–28%" | Corrected to the modelled figure |
| 9 | CNG km/kg sensitivity applied to the wrong vehicle | Claimed "CNG mileage doesn't matter" — false |
| 10 | Removed Delhi EV road-tax waiver on a draft-policy source | **Penalised the EV by ₹1,27,260** |
| 11 | Source count stated as 31, then 35 | Corrected — now 53 |
| 12 | **Tornado routed CNG-side parameters to the EV vehicle** | **`CNG residual 40→45%` reported +26.0%; correct value +12.8%.** `km/kg` and `price` rows were silently ignored and printed base results that looked like real null effects |
| 13 | **Depot charging infrastructure excluded from the boundary while being the document's load-bearing condition** | **Headline −9.3 pp at 5 yr (−10.8 pp at 8 yr). Falsified "wins in every city"** |
| 14 | **₹11/km described as both "net fare" and "gross revenue"; a non-existent 20–25% commission excluded as if live** | **Driver take-home overstated by ₹1,742/mo. Corrected to the flat ₹67/day fee.** Delta unaffected |
| 15 | **Cash purchase compared to financing on nominal cash flows** | **+22.6% cash premium does not survive a 12% discount rate** |
| 16 | **"45 hours/month of headroom" was a breakeven threshold presented as slack** | **True slack is 21.9 h/month beyond a 3.5 h baseline; lost-hour rate was ₹112, derived rate is ₹200.46** |
| 17 | **Operator-owns-the-vehicle argument presented alongside EMI-as-driver-outflow without separating the two** | **Now split into explicit driver-owned and fleet-owned models. Owner-level delta identical (₹0)** |
| 18 | **~198 EFC/yr mixed wall energy with nominal capacity** | **Overstates EFC by 11.1%. Correct basis is 178.0. Battery report unchanged** |
| 19 | Appendix cited a `/tmp` path that no longer existed | Now points at the working directory |

---

## 14. Convergence analysis

Fifty-three sources, listed in 51 numbered entries — entries 46 and 47 each cite two papers.
Where they agree, the finding is safe to present. Where they diverge, the
divergence is disclosed.

### Where the literature converges

| Finding | Converging sources |
|---|---|
| **EV is most cost-effective for high-mileage taxis** | CEEW · Cadmus/Uber · ICCT · BusinessLine · ev.care |
| **Parity threshold ~100–200 km/day** | BusinessLine (EKA, Euler) · CEEW · ev.care |
| **EV maintenance 40–70% below ICE** | EVSelect · ev.care · CEEW |
| **EV tyres wear 25–30% faster** | EVSelect · ev.care |
| **EV residual materially weaker than ICE** | BluSmart · Mahindra First Choice · Spinny · CARS24 · JATO |
| **Depot charging is essential, not optional** | ev.care · Indian Express · Cadmus/Uber |
| **CNG real-world 22–27 km/kg in metro taxi duty** | cars24 · buyselltaxi · CarTrade |
| **Commission has moved from per-ride % to flat daily fee** | Economic Times · Times of India · Inc42 · BusinessLine |
| **Depot AC overnight charging is per-port cheapest** | ev.care · My EV Charger · EV Hub Studio · Magma ChargeSpot |

### Where sources diverge

| Disagreement | Positions | What we did |
|---|---|---|
| **EV residual: level vs trend** | Mint 2024: Nexon EV depreciation *improving* 51% → 26%. Mint 2025 + Business Standard: still ~2× worse than ICE. BluSmart: 26% realised | Both true — absolute depreciation falling while the *gap* persists. Modelled **26%** |
| **Payback period** | BusinessLine **18–24 mo**; ev.care **2–3.5 yr** (3W) / **2.5–4 yr** (charging infra) | Scope differs — BusinessLine is light-CV fleet parity, ev.care includes charger capex. We use **fleet-car** figures |
| **Battery replacement in horizon?** | CEEW assumes packs replaced after ~2,500 cycles. Our battery phase: 178 EFC/yr → 3,000 cycles ≈ **16.9 yr** | **No replacement modelled** in 8 yr; flagged in §12 |
| **EV energy ₹0.64 or ₹1.71/km?** | Delhi EV tariff ₹4.50 vs public DC ₹12–24 | Both true — **this is the routing decision**, not a disagreement |
| **Delhi EV road tax** | Secondary compilation (draft): waiver lapsed Mar 2026. Notified Policy 2026: **full life-time waiver** | **Notified policy wins.** 0% modelled |
| **Electricity escalation** | CEA LT commercial CAGR **5.1%/yr** (2014–24); MERC 2026 MYT order **cuts** Maharashtra tariffs to 2030 | Modelled **4.5%/yr**, below the CEA historical rate, with MERC disclosed as a counter-case |
| **CNG escalation** | CERC notified **3.46%/yr**; PNGRB APM trajectory **3.47%/yr** | Convergent. Modelled **3.5%** |

**Honest summary:** sources agree on direction and mechanism. The magnitude disagreements cluster
on *charging arrangement* and *residual assumption* — the two things flagged here as conditions
rather than settled facts.

---

## 15. Risks, in order of size

| Risk | Exposure | Mitigation |
|---|---|---|
| **Pack replacement inside the horizon** | **₹4 L → −4.5% · ₹8 L → −23.5% · ₹12 L → −42.6%. Any replacement flips the answer.** | Warranty-backed pack-to-pack or capacity-retention guarantee |
| **Charger cost above assumption** | Mumbai already past break-even at ₹99,000; Bengaluru has only ₹16,197 of headroom | Negotiate a fleet charger rate; sub-₹96,000 port required for Mumbai |
| **Charging moves depot → public** | −1.4% at ₹12/kWh; −26.8% at ₹24 | Depot charging as a contractual operating premise |
| **Holding period shortens to 5 years outside Delhi** | Mumbai −0.2% to −1.4%; Bengaluru −0.4% to +0.9% | 7-year tenure, or duty above 195 km/day, or Delhi-first |
| **Uptime falls to Green SM levels** | 75 h/month against 21.9 h of real slack — **EV loses 28.4%** | Charger redundancy (N+1), guaranteed-response maintenance SLA |
| **Residual lands at deck's 36% or below** | −6.1 points | OEM buyback at ≥36% |
| **Duty falls below ~162 km/day** | EV loses (Delhi, 5yr, with infrastructure) | Our duty is 200 km/day; re-run this model if it changes |
| **Electricity above ~₹11/kWh** | −1.4% at ₹12 | Depot tariff as a contracted premise |
| **Demand charges on an HT depot contract** | −1.5 pp at ₹500/veh/mo | LT connection; negotiate demand terms |
| **Consumption is the deck's 15.38** | −1.8 points only | Small. Verifiable from telematics in month one |
| **Financing at 10% for 60 months** | Costs ~8 points vs cash on a nominal basis | Negotiate 7-year tenure or an EV-specific product |

**Three of the top four risks are operational or contractual; none is a property of the
powertrain.** The honest headline: the vehicle is right, and the business case is held together
by how it is charged, financed and warranted.

---

## 16. What we will not claim

- **Not** "the EV is 14.5% cheaper." With depot infrastructure on the stated boundary the figure
  is **+6.7%** over 5 years and **+14.6%** over 8, in Delhi.
- **Not** "the EV wins in every city modelled." It does not, at five years, outside Delhi. Four
  of 48 cells are negative and we have printed them.
- **Not** "the cash-purchase advantage is +22.6%." That is a nominal cash-flow comparison and
  does not survive discounting.
- **Not** "cheap financing rescues a short holding period outside Delhi." It does not. On the
  NPV basis financing actually *helps* the EV, and Mumbai is still negative after it.
- **Not** "the CNG mileage assumption doesn't matter." It does — from +19.5% to +7.6% across the
  realistic band.
- **Not** "zero downtime cost." The base case is 3.5 h/month and the real slack is 21.9 h/month,
  against a documented 75 h/month failure mode.
- **Not** "residual value is fine." We use 26%, the pessimistic realised number.
- **Not** "no battery cost inside the horizon." A ₹4 L replacement reverses the case.
- **Not** a driver-income argument as the lead. Lead with the operator case.

---

## 17. Sources

**TCO methodology and parity**
1. CEEW, *Cost of Ownership for India's Road Transport Sector* — taxi TCO ranking; maintenance sensitivity
2. Cadmus / Uber, *Electrifying Ridehail in India* (Jan 2026) — opportunity cost of charging
3. ICCT, *Near-term incentives for electrifying India's four-wheeler ride-hailing fleet* (2021)
4. ICCT, *Updated analysis of incentives* (2021)
5. Electricon / Industry Report (2025) — TCO model with battery replacement and salvage terms
6. Ola Institute, *Beyond Nagpur* — fleet TCO logic
7. The Hindu BusinessLine (26 Feb 2026) — parity at 120–200 km/day

**Charging infrastructure — costed in this revision**
8. My EV Charger, *EV Charger Price in India* — hardware vs installed cost by charger class
9. ev.care, *EV Fleet Depot Charging Setup in India* (Jun 2026) — AC vs DC, simultaneity, overnight sizing
10. EV Hub Studio, *EV Charging Station Cost in India 2026* — CAPEX breakdown; demand charges above 50 kW
11. Magma ChargeSpot, *How Much Does It Cost to Start an EV Charging Business in India* (Sep 2026)
12. Godrej Capital, *EV Charging Station Business in India* (May 2026) — component cost table
13. RIOD, *EV Charger Price India 2026* — installation cost scenarios
14. Exicom, *EV Charging Station Setup — reality breakdown* (Dec 2025) — multi-charger depot totals
15. Bureau of Energy Efficiency, *State-wise EV Tariff* annexure — Delhi LT 4.50 / HT 4.00
16. MERC / MSEDCL multi-year tariff order (Mar 2026)
17. ev.care, *EV Fleet Management Guide* (Jun 2026) — energy ₹1–1.5/km; downtime risk
18. SBI, *E-mobility and charging infrastructure in India* — charger counts, utilisation
19. The Indian Express (1 Sep 2026) — Green SM Limo Noida downtime, ~2.5 h/day

**Platform economics — corrected in this revision**
20. The Economic Times (18 Jun 2025) — Ola zero-commission pan-India, drivers keep 100% of fare
21. Economic Times / The Hindu BusinessLine (8 May 2026) — Ola Consumer FCF positive; subscription model replaces per-ride commission
22. Times of India (23 Jun 2025) — flat-fee economics; Redseer driver income data (₹2,400/day gross, ₹58,325 net)
23. Inc42 (13 Aug 2025) — Uber zero-commission cab pilot; 72-hour pass ₹341 incl. 18% GST
24. CNBC TV18 (19 Feb 2025) — Uber/Ola subscription shift; Namma Yatri ₹90/day cabs
25. ET Now (17 May 2026) — CEA proposal on fixed-charge recovery

**Escalation rates — added in this revision**
26. CERC, notification 16 Apr 2026 — domestic gas escalation **3.46%/yr**
27. PNGRB, *Natural Gas Projections — 2030 Base Case* — APM ceiling +$0.25/financial year
28. CEA tariff data 2014–2024 — LT commercial CAGR 5.1%/yr
29. The Indian Express (27 Mar 2026) — MERC approves annual tariff *cuts* to 2030 (counter-case)

**Residual value**
30. Mint (25 Apr 2025) — Spinny and CARS24 depreciation data
31. Mint (5 Sep 2024) — JATO Dynamics Nexon EV depreciation trend
32. Business Standard (24 Oct 2025) — IRDAI IDV table; no EV-specific standard
33. The Hindu BusinessLine (10 Jul 2026) — pre-owned EV market
34. The Core (16 Jun 2026) — battery certification gap; Policybazaar on insurance
35. Mahindra First Choice — EV residual 70–80% of ICE at 3 years
36. **BluSmart (Anmol Jaggi)** — assumed 10% residual, realised 26%

**Maintenance and insurance**
37. EVSelect, *EV Car Maintenance & Service Cost in India* (Jun 2026) — service −40–60%; tyres +25–30%
38. CEEW — maintenance sensitivity
39. Policybazaar — EV OD premium higher; 15% discount is third-party only

**Tax and policy**
40. GST 2.0 (effective 22 Sep 2025) — EV 5%, small car 18%
41. Business Today (3 Sep 2025) — GST rate restructuring
42. **Delhi Electric Vehicles Policy 2026** (approved 29 Jun, notified 30 Jun 2026, effective 1 Jul 2026, to 31 Mar 2030) — primary sources: JSA Prism legal analysis; Indian Express; New Indian Express; HT Auto
43. Karnataka / Maharashtra / Delhi state road-tax schedules 2026
44. PIB (4 Sep 2025) — road passenger transport GST options
45. Delhi EV gazette SG.DEL-E.29112023-250308 — fleet electrification by 1 Apr 2030

**Battery physics**
46. Naumann 2018 (`10.1016/j.est.2018.01.019`) · Lewerenz 2017
47. Eldesoky 2022 (`10.1149/1945-7111/ac99a6`) · Harlow 2019 (`10.1149/2.0981913jes`)

**CNG comparator — measured fuel economy**
48. cars24, *Maruti Suzuki Dzire real world mileage* (Apr 2026)
49. buyselltaxi, *Dzire CNG mileage real world — Delhi taxi 2026* (May 2026)
50. CarTrade, *Swift CNG real-world road test* (May 2025) — city 21.28, highway 35.01 km/kg
51. CarFurious, *Best car for Ola/Uber drivers 2026* — Tour S real-world 26–30 km/kg

---

## Appendix — Reproducing every number

Engine `~/Downloads/MACH1_WORKING_FILES/tco_engine/tco_engine.py` · analysis
`~/Downloads/MACH1_WORKING_FILES/tco_engine/tco_analysis.py`

Run `python3 tco_analysis.py`. Sections A–F reproduce the vehicle-only model; **G** infrastructure;
**H** NPV and escalation; **I** downtime decomposition; **J** ownership models; **K** EFC definition;
**L** headline consistency matrix; **M** city × basis matrix.

```
DUTY      200 km/d x 26 d x 312 d = 5,200 km/mo | 62,400 km/yr | 312,000 km (5 yr) | 499,200 km (8 yr)
EV on-road 12,12,000 x 1.05 GST x 1.00 Delhi EV road tax (exempt) = Rs12,72,600
CNG on-road 6,56,000 x 1.18 GST x 1.10 Delhi road tax               = Rs 8,51,488
EV energy  12.84 kWh/100km x 4.50 / 0.90 charge efficiency = Rs0.64/km -> Rs2,00,304
CNG energy 312,000 / 25 km-per-kg x Rs76/kg                = Rs9,48,480
EV  EMI   Rs12,72,600 x 10%/12 over 60 mo                 = Rs27,039/mo
Charger  (Rs50,000 port + Rs30,000 install + Rs10,000 load) x 1.1 redundancy = Rs99,000
Charger opex Rs12,000 CMS + Rs3,000 AMC = Rs15,000/yr, escalated 4%/yr
Net fare  Rs11.00 - (Rs67 x 26)/5,200                     = Rs10.665/km -> Rs55,458/mo
EFC       12.84 kWh/100km x 62,400 km = 8,012 kWh/yr / 45 kWh nominal = 178.0 EFC/yr
Downtime  (220.00 gross - 6.70 platform - 12.84 energy avoided)/h = Rs200.46/h
5-yr infra-inclusive Delhi, NPV 12% escalated : EV Rs15,67,287  CNG Rs16,79,260 -> +6.7%
8-yr infra-inclusive Delhi, NPV 12% escalated : EV Rs18,73,852  CNG Rs21,94,045 -> +14.6%
```

Every table in this document is regenerated by running that script. No figure was transcribed by
hand.