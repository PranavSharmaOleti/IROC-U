# Powertrain & Energy Strategy + Technical Specifications
### Supporting analysis for Item 3 and Item 4 — MACH1 / FleetLine E1

---

## 0. Bottom line

**Your verdict is right: BEV. Keep it.**

But the deck argues it with the wrong evidence and omits the one condition that makes it true.

Three findings matter more than anything else in this document:

1. **BEV wins on operator cost per kilometre by 16–28%, and it wins across the entire plausible CNG fuel-economy range.** That is a far stronger argument than the one currently in the deck.
2. **The deck's "TCO" table is mislabelled.** The numbers are *driver take-home earnings*, not cost. A judge reading "TOTAL COST OF OWNERSHIP" and seeing the EV column higher will conclude the EV is more expensive. It is the opposite.
3. **BEV only works here because this is a return-to-base fleet that can charge overnight.** That dependency is load-bearing and the deck never states it. The entire field record of EV ride-hailing failure in India is what happens when that condition is missing.

---

## 1. The verdict, and the condition attached to it

| | |
|---|---|
| **My verdict** | **BEV, LFP, single-speed reduction drive — as you have it.** |
| **Agreement** | I reached the same conclusion independently from the sources below. |
| **Condition** | The vehicle is viable **only** under return-to-base operation with depot AC charging overnight. This must be stated as a design premise, not assumed. |
| **What I would change** | The *argument*, not the *answer*. Three things in the deck need correction (§9). |

I did not find a case for HEV, PHEV, CNG, or Bio-CNG that beats BEV for *this* duty cycle. §7 shows why, one option at a time.

---

## 2. The comparison that actually decides it

The brief asks for justification on four axes. Here is the full matrix.

| | **BEV** | **HEV** | **PHEV** | **CNG** | **Bio-CNG** |
|---|---|---|---|---|---|
| **Cost/km (operator)** | **₹6.42** | ₹9–11 | ₹8–10 | ₹7.42–8.34 | ≈ CNG + supply risk |
| **Refuelling readiness** | Depot AC overnight; **zero** revenue-hour downtime if designed | Full — ICE base | Full — ICE base | **Best-in-class**, ubiquitous, 3–5 min | Same hardware as CNG, feedstock-constrained |
| **Range / uptime** | 315 km real (verified) — covers 200 km/day with margin | Unaffected | Unaffected | ~500–600 km real | ≈ CNG |
| **Sustainability** | Best available on a coal-heavy grid; zero tailpipe | Marginal | Marginal | Methane slip; worse CO2 | Genuinely low-carbon — but supply immature |
| **Chosen by regulators** | **Yes** — Delhi gazette 100% by 2030 | No | No | No | No |
| **Verdict for this duty** | **SELECT** | Reject | Reject | Runner-up | Reject for 2035 |

**Read the top-right of that table carefully.** CNG wins decisively on refuelling readiness and range-for-money. BEV beats it on *running cost* and *regulation*, and that is what wins here — **because the duty cycle is high enough to amortise the capital premium.**

That threshold is documented, not guessed:

> *"Total cost of ownership parity with diesel often emerges when vehicles run **120–200 km daily**, with payback in roughly 18–24 months… economic parity can begin at **100–150 km per day** depending on tariffs and financing structures."*
> — The Hindu BusinessLine, 26 Feb 2026, quoting EKA Mobility and Euler Motors

**Your duty assumption is 200 km/day — the top of that band.** The choice is not marginal; it is the single most favourable duty cycle in the Indian market for electrification. That is the strongest single argument available to you, and the deck does not make it.

Corroborated by CEEW:

> *"For taxis, high annual mileage makes EVs the most cost-effective option, followed by CNG where infrastructure exists."*

---

## 3. Cost — the real argument

### 3.1 What the deck currently shows, and why it is mislabelled

The deck's table is headed **"APPROXIMATE TOTAL COST OF OWNERSHIP."** The rows are monthly revenue, EMI, energy, maintenance, insurance, and **"net take-home."** Net take-home is *revenue remaining after costs* — it is earnings, not cost. **Higher is better.**

So the EV column reads ₹9.81 L vs CNG ₹8.16 L, and under a "TCO" heading that looks like the EV costing *more*. It is actually ₹1.65 L *better*.

**This is the highest-risk item in the deck.** It is a label that inverts the meaning of the headline number, and it is the kind of thing a judging panel catches.

(There is also a small arithmetic slip: the deck prints EV take-home **₹16,380**; the proposal prints **₹16,360**; the inputs produce **₹16,360**.)

### 3.2 The right metric: operator cost per kilometre

Your customer is Ola, Uber, or BluSmart — not the driver. They buy on **cost per kilometre including asset cost and residual**. Recomputed on the deck's own assumptions (200 km/day, 26 days/month, ₹8/unit, CNG ₹90/kg):

| | **EV** | **CNG** |
|---|---|---|
| Vehicle on-road | ₹14,00,000 | ₹8,51,465 |
| Energy over 5 yr (312,000 km) | ₹3,20,486 *(40,061 kWh @ 12.84)* | ₹11,23,200 *(12,480 kg @ 25 km/kg)* |
| Maintenance, 60 months | ₹72,000 | ₹2,10,000 |
| Insurance, 60 months | ₹2,10,000 | ₹1,97,400 |
| **5-year gross** | **₹20,02,486** | **₹23,82,065** |
| **Cost/km, gross** | **₹6.42** | **₹7.63** |
| **Cost/km, less residual** (EV ₹5 L / CNG ₹3 L) | **₹4.82** | **₹6.67** |
| **EV advantage** | **16% gross / 28% net of residual** | |

### 3.3 It is not knife-edge

CNG fuel economy is the biggest single assumption in the CNG column. Sensitivity:

| CNG mileage | CNG cost/km | EV advantage (gross) |
|---|---|---|
| 20 km/kg (pessimistic) | ₹8.34 | **23%** |
| 25 km/kg (assumed) | ₹7.63 | **16%** |
| 30 km/kg (optimistic) | ₹7.42 | **13%** |

**EV wins across the entire plausible range.** The conclusion does not depend on the assumption. That is the thing to say to a judge who challenges it.

### 3.4 What the deck's TCO omits — and should not hide

Uber's own India TCO framework (Cadmus, Jan 2026) includes a term the deck leaves out:

> *"The analysis includes vehicle depreciation, fuel, insurance, maintenance, and **the opportunity cost of charging (i.e., foregone wages due to time spent charging)** over a four-year ownership period."*

This is the largest risk term in the whole comparison, and ICCT showed that in 2020 it was large enough to make BEV ₹3.72/km *more expensive* than CNG in Delhi. It shrinks to near zero **only if the vehicle charges overnight at its depot.** §5 is therefore not a footnote — it is the argument.

---

## 4. Range and energy — the deck under-sells itself

### 4.1 Your 263 km figure is conservative

The deck derives 263 km from 45 kWh at 15.38 kWh/100 km. That consumption figure was **already corrected downward to 12.84 kWh/100 km** in the battery-phase analysis, against the verified duty cycle. On the corrected figure:

| Basis | Consumption | Range (45 kWh, 90% usable) |
|---|---|---|
| Deck's own | 15.38 kWh/100 km | 263 km |
| **Corrected (verified duty)** | **12.84 kWh/100 km** | **315 km** |

**You have 315 km, and you are claiming 263 km.** For a jury that means you are being conservative, which reads as rigor. You may also just claim 315 km and note the basis — but do not present the two without saying which duty cycle each comes from.

### 4.2 The battery-life claim in the survey is wrong — in your favour

Your survey document states:

> *"BYD Blade LFP cycles to 80% retention at ~3,000 cycles… At 365 cycles/year, that's 8.2 years."*

**You do not do 365 cycles per year.** At 200 km/day and 12.84 kWh/100 km you consume 25.7 kWh/day against 40.5 kWh usable — that is **0.63 cycles/day, or ~198 cycles/year.**

| | Survey claim | Corrected |
|---|---|---|
| Cycles/year | 365 | **~198** |
| 3,000 cycles lasts | 8.2 years | **~15 years** |

The survey's own table therefore shows the pack comfortably outlasting the loan — and the error made the pack look *worse* than it is. Correct it.

### 4.3 But do not over-claim, and here is why

The battery-phase work established something the deck does not carry: **an 8-year / 80% warranty is not defensible at 40 °C cell temperature.** Two peer-reviewed LFP studies disagree by 3.6× on long-horizon behaviour —

- **Naumann 2018** (√t law) → **13.3 years** to 80% at 40 °C
- **Lewerenz 2017** (linear law) → **3.7 years**

Both are LFP, both are defensible, and the model reproduces Lewerenz's own "3–4 years" figure independently. A vendor cycle-life number quoted at 25 °C is not a warranty at 40 °C.

**Consequence for this section:** state the pack's *first-life* chemistry and thermal design confidently, and carry the warranty exposure explicitly as a separate line — exactly as the battery report does. Do not let a 3,000-cycle vendor spec become the load-bearing claim.

### 4.4 Pack sizing headroom

| Duty | Pack needed (12.84 kWh/100 km, 75% usable) |
|---|---|
| 200 km/day | 34 kWh → **45 kWh is comfortable** |
| 263 km/day | 45 kWh |
| 300 km/day | **51 kWh** → 45 kWh would not close the day |

This is why the duty-cycle contradiction in §9.3 matters.

---

## 5. Charging and refuelling readiness — the load-bearing dependency

### 5.1 Why this is the decisive axis, not the energy cost

India has roughly **35,000 public charging ports for 5.7 million registered EVs — 160 EVs per port** (NITI Aayog index, via Cadmus/Uber). China is at ~10, EU at ~13. Station utilisation runs **1–3%** against a 10–15% break-even (SBI sector report, 2026).

Public charging is therefore not an operating plan for a fleet. It is a fallback.

### 5.2 The field evidence — what actually happens without depot charging

> *"Around two-and-a-half months after… Green SM launched its electric taxi service… drivers said they are spending hours waiting for chargers or going offline to conserve battery… I sometimes come to charge my vehicle on my week-offs."* — The Indian Express, 1 Sep 2026, Noida

That operation reports **2.5 hours a day** lost to queueing, drivers going offline at 15% charge, and 100–150 cars queuing at a single 12-charger site. **This is the failure mode to design against, and it is well documented.**

### 5.3 The condition that makes BEV work here

Your duty is **return-to-base** — 26 days a month, overnight at a depot. That is the best possible case for AC charging:

| Charger | Time for 36 kWh (10→90%) | Fits an overnight window? |
|---|---|---|
| 7.4 kW AC | 4.9 h | **Yes** |
| 11 kW AC (3-phase 32 A) | 3.3 h | **Yes** |
| 22 kW AC | 1.6 h | **Yes** |

**At any of these, the vehicle is fully charged before the shift and loses zero revenue-hours to charging.** That is the single most important sentence in this section.

It is also worth what everyone else pays for it:

| Charging route | Cost |
|---|---|
| Public DC fast charge | ₹18–24 /kWh |
| Depot, off-peak commercial tariff | **₹5.50–9 /kWh** |
| Depot + rooftop solar | ₹3–5 /kWh |

Time-of-day tariffs apply to commercial loads above 10 kW. **Smart off-peak scheduling cuts charging cost 20–35%** — and demand charges (₹40–190/kVA/month) are managed by load spreading, not by buying more chargers. A **1:3 charger-to-vehicle ratio** is achievable with shift-based scheduling; over-buying DC ports that sit idle overnight is the classic fleet waste.

### 5.4 Comparative readiness

| | Refuel/recharge time | Availability | Revenue-hours lost |
|---|---|---|---|
| **CNG** | 3–5 min | Ubiquitous in metros | **~0** |
| **Bio-CNG** | 3–5 min | Hardware same as CNG; **supply immature** | ~0 when available |
| **BEV (depot AC)** | 3–5 h, **overnight** | Build your own | **0** |
| **BEV (public DC)** | 30–90 min + queue | Sparse | **1–3 h — measured** |

CNG is genuinely better at this one axis, and in a 16-hour double-shift operation without a depot it *would* win. You have a depot. Use it.

---

## 6. Sustainability

Being precise, because the usual framing is wrong in both directions:

| Pathway | Verdict |
|---|---|
| **BEV, India grid today** | ~50–60% below petrol well-to-wheel. **Not zero.** India is ~75% coal. Saying "zero emissions" is false; saying "tailpipe zero" is true. |
| **BEV + renewable depot supply** | Approaches zero operational carbon. Solar carport at ₹3–5/kWh is viable at fleet scale. |
| **CNG** | Cleaner at the tailpipe than petrol, but **methane slip** in extraction and processing carries a ~80× GWP penalty over 20 years. |
| **Bio-CNG** | Genuinely low-carbon — captured biogas avoids methane. **But see below.** |
| **HEV / PHEV** | Marginal. Most of the carbon benefit of an efficient petrol engine is available in a well-designed HEV. |

The honest BEV argument is therefore **two-part, and both parts must be said:**

1. **Street-level air quality.** Zero tailpipe emissions in Delhi NCR, where the city's air quality is the binding constraint and where clean-vehicle mandates are already gazetted to 100% new-fleet onboarding by **1 April 2030** (Delhi gazette SG.DEL-E.29112023-250308).
2. **Carbon, improving on a curve.** Roughly half the petrol advantage today, and the fleet controls its own electricity supply — so it can choose to buy renewable. A CNG fleet cannot choose its feedstock; it buys whatever the pipeline has.

That second clause is the one to make. **A depot-owning fleet can decarbonise its own electricity.** A gas fleet cannot.

---

## 7. Why not the alternatives

### 7.1 CNG — the real competitor, and it loses on cost

CNG wins refuelling readiness and has a far lower purchase price. It loses because **at 200 km/day the running-cost saving is not enough to cover the ₹5.49 lakh capital premium within five years** — it takes roughly that long, after which EV wins for the remaining life.

It remains the **fallback**, and that is a legitimate position: if depot charging fails, CNG is the operating plan. Say so explicitly. A proposal with a named fallback is stronger than one that pretends to certainty.

### 7.2 Bio-CNG — the option that is not ready

Bio-CNG has the best carbon story of any fuel available, and it is **not deliverable at fleet scale in 2035**:

- **207 CBG plants commissioned as of April 2026**, against a government target of **5,000** by 2030
- **Only 17 of those 207 are pipeline-connected** — the rest move by high-pressure cascade
- Commissioned capacity is **~2 MMTPA against a 15 MMTPA target**
- Operating plants run at **20–60% of rated capacity** on feedstock inconsistency
- Mandatory blending is only **1% in FY2025-26, rising to 5% by FY2028-29**

*(Sources: PNGRB CBG reports; Deloitte/PNGRB CBG session paper, 2025–26)*

**Reject for a 2035 launch, keep as a post-2035 watch item.** If asked, the answer is: not a supply problem, a feedstock-logistics problem, and the 5,000-plant target is itself an aspiration.

### 7.3 HEV and PHEV — structurally uncompetitive here

CEEW is unambiguous:

> *"Petrol-electric hybrid vehicles… are significantly more expensive, mainly due to the high GST and compensation cess (**at 43 per cent**), making them uncompetitive in this segment against EVs."*

The tax treatment alone is disqualifying. Beyond that, both inherit the ICE's full mechanical service burden — the exact cost line where EV gains its advantage — while adding a battery and inverter to a fleet that will keep both. For a fleet that owns its vehicles and services them at scale, **HEVs are the worst of both worlds: ICE running costs plus two new failure modes.**

### 7.4 Why not a mix

A mix is defensible *across markets* but not *within one vehicle programme*. Your customer's problem is not "choose a chemistry" — it is "one asset, one service network, one training pipeline." Maruti's own advantage is a single service ecosystem. Splitting it across two powertrains destroys the thing that makes the fleet business work.

**Single powertrain: BEV.** With CNG named as the operational fallback.

---

## 8. Technical Specifications (Item 4)

Deck specifications are reproduced as **proposed**. Deltas are what I recommend changing, with the reason.

### 8.1 Range and energy

| Item | Proposed | Recommended | Note |
|---|---|---|---|
| Battery chemistry | LFP | **LFP** ✅ | Cycle life, thermal margin, cost. Chemistry locked per battery report. |
| Pack capacity | 45 kWh | **45 kWh** ✅ | Covers 200 km/day at 34 kWh with headroom. |
| Usable window | — | **10–90% (36 kWh)** | Reserving 5% top and bottom protects cell life. |
| Claimed range | 263 km | **263 km** (conservative) | True range ~315 km at verified consumption. |
| Consumption basis | 15.38 kWh/100 km | **12.84 kWh/100 km** | Corrected in battery phase. State which basis each figure uses. |
| Daily energy | — | **25.7 kWh @200 km/day** | Add an AC-load sensitivity line. |
| **AC / aux energy** | **not specified** | **Add: 20–35% of drive energy at 45 °C** | ⚠️ **Gap.** Your deck itemises HVAC 9.60 + aux 2.80 + TMS 2.40 = **14.80 kWh/day**, which does not reconcile with 12.84. Resolve before printing. |

### 8.2 Battery / energy system

| Item | Proposed | Recommended |
|---|---|---|
| Motor | 80–100 bhp PMSM | **80 bhp continuous / 100 bhp short-duration peak**, water-cooled |
| Drive | Single-speed reduction | ✅ Unchanged |
| Motor efficiency | 93–97% peak | ✅ |
| Hot-weather efficiency | −1–2% at 45 °C | ✅ (motor only — see below) |
| **Peak vs continuous rating** | not distinguished | ⚠️ **Add.** At 45 °C ambient the continuous rating derates; specifying only "80–100 bhp" is ambiguous. |
| **Pack thermal management** | **not specified** | ⚠️ **Add: active liquid cooling, pack kept ≤45 °C.** Non-negotiable — the battery model is calibrated on 40–48 °C cell temperature, and Indian summer ambient makes this the primary durability constraint. |
| Peak charge rate | 1–2C | ✅ 45 kWh @ 1C = 45 kW. |
| **Overnight charging** | **not specified** | ⚠️ **Add: 11 kW AC, 3-phase, ≥3 h window.** This is the operating premise (§5.3). |

### 8.3 Safety

| Item | Proposed | Recommended |
|---|---|---|
| Airbags | ✅ | Retain |
| ABS | ✅ | Retain |
| **ESC** | **absent** | ⚠️ **Add Electronic Stability Control.** 1.4 t sedan, Indian road conditions, monsoon — and increasingly expected in fleet procurement. |
| ADAS | Level 2 | Retain; justify as **driver-load reduction** in a 16-hour shift |
| **EV safety compliance** | not specified | ⚠️ **Add: AIS-156 (thermal propagation), AIS-038 Rev.2 (EV powertrain safety), ECE R100.** The battery report already establishes the AIS-038 chemistry-change pathway — carry it. |
| **BMS** | "intelligent" (AI section) | ⚠️ Specify **cell-level voltage/temperature monitoring + microprocessor BMS**, not just an AI layer. |

### 8.4 Durability for commercial duty

This is the section where a fleet buyer actually reads closely, and it is currently thin.

| Item | Proposed | Recommended |
|---|---|---|
| Rated drive-unit life | 200,000+ km | ⚠️ **Flag.** At 62,400 km/yr that is **3.2 years.** Either restate as a time-based rating or state the replacement assumption. Do not leave a 200,000 km claim next to a 62,400 km/yr duty without comment — a fleet buyer will do that division. |
| Primary wear item | Bearings | ✅ Retain |
| **Battery first-life** | ~15 yr (corrected) | ⚠️ **Split from warranty.** Life and warranty are different claims; the battery report shows warranty is the uncertain one. |
| **Corrosion / thermal** | not specified | ⚠️ Add: subframe and battery-enclosure corrosion class; validated for coastal and monsoon deployment. |
| **Service interval** | not specified | ⚠️ Add: interval expressed in **months, not km** — a high-km vehicle will otherwise over-serve worn components. |
| **Vibration / NVH** | not specified | ⚠️ Add: validated to IS/ISO durability profiles. Your own technical exhibits include vibration monitoring, so the vehicle spec should match. |

### 8.5 Comfort and interior

| Item | Proposed | Recommended |
|---|---|---|
| Seating | 5-seat, 2-row | ✅ |
| Rear AC vents | ✅ | ✅ Genuine fleet differentiator — keep it prominent |
| Flat floor | ✅ | ✅ EV advantage, keep it |
| Ventilated seats | ✅ | ✅ Justified by AC-load sensitivity |
| Upholstery | Durable leatherette | ✅ |
| Steering | EPS | ✅ |
| Panoramic sunroof | Top variant | ⚠️ Reconsider for fleet — adds cost, weight and thermal load for no rental benefit. |

### 8.6 Interior and luggage space

| Item | Proposed | Recommended |
|---|---|---|
| Boot | 400 L *(deck graphic says 420 L)* | ⚠️ **Resolve the inconsistency — one number only.** |
| Rear seat | Priority (paying passengers) | ✅ Correct read of the business |
| Floor / tunnel | Flat, no tunnel | ✅ |

---

## 9. Corrections required before you present this

### 9.1 Relabel the TCO table — highest priority
It is a **driver-earnings** table under a **cost** heading. Relabel to "Driver Net Take-Home" and add a separate operator **cost/km** table from §3.2. Left as is, it argues against you.

### 9.2 Fix the range/consumption reconciliation
15.38 vs 12.84 kWh/100 km appears in different places with no note. Pick the verified figure as primary, state the basis, and note that the pack is good for ~315 km.

### 9.3 Resolve the duty-cycle contradiction
Deck and proposal say **200 km/day**. Your survey says **"vehicles operate 16 to 18 hours daily (250–300 km/day)."**

At 300 km/day a 45 kWh pack does **not** close the day on one charge — it needs ~51 kWh, or mid-shift charging, which reintroduces exactly the downtime that damages the TCO.

**Pick one number.** The recommendation is **200 km/day + return-to-base**, because that is the case where BEV wins outright. If 250–300 km/day is real, either enlarge the pack or introduce opportunity charging and re-run the TCO with a downtime term.

### 9.4 Correct the cycle-life arithmetic
365 cycles/yr → **~198 cycles/yr**. 3,000 cycles is ~15 years, not 8.2 (§4.2).

### 9.5 Add the two missing specs
**ESC**, and **pack thermal management**. The second is not cosmetic — the entire durability model is calibrated on a 40–48 °C cell temperature.

### 9.6 State the operating premise
Add one line to the deck: *return-to-base, overnight depot AC charging.* Without it the vehicle is not viable and nothing in §5 has been earned.

### 9.7 Resolve the HVAC energy line
Deck itemises 14.80 kWh/day (HVAC 9.60 + aux 2.80 + TMS 2.40); the verified duty is 12.84 kWh/day. The gap is roughly the AC load — legitimate, but it must be stated rather than inconsistent.

---

## 10. What we will not claim

In the spirit of the battery report:

- **Not** "zero-emission vehicle." Tailpipe zero, on a ~75% coal grid. Say "zero tailpipe."
- **Not** that 263 km is our range. It is a conservative claim; real range is higher on the corrected duty cycle. Say which is which.
- **Not** that the pack is warrantied for 8 years / 80%. Two peer-reviewed LFP studies differ by 3.6× on that at 40 °C.
- **Not** that EV wins in every city. CEEW notes EV taxis lead in Delhi with widespread charging and are "yet to become popular" elsewhere — **charging geography is the variable, not chemistry.**
- **Not** that Bio-CNG is unavailable. It is unavailable *at scale, on schedule.* The 5,000-plant target is real policy; the pipeline is not.
- **Not** that hybrids are technically inferior. They are **taxed into** uncompetitiveness at 43%. That is the argument; not capability.

---

## Appendix A — Sources

**Powertrain / TCO / economics**
- CEEW, *Cost of ownership for road transport sector for different vehicle segments, fuels and powertrains* — taxi TCO ranking; hybrid 43% GST+cess.
- Cadmus / Uber, *Electrifying Ridehail in India* (Jan 2026) — opportunity cost of charging; 35,000 ports / 5.7 M EVs (NITI Aayog); EV-to-port ratios; off-peak tariffs.
- ICCT, *Near-term and updated incentives for electrifying India's four-wheeler ride-hailing fleet* (2021) — TCO methodology; charging-time sensitivity; historical gap vs CNG.
- The Hindu BusinessLine, 26 Feb 2026 — fleet TCO parity at 120–200 km/day; return-to-base parity at 100–150 km/day.
- Ola Institute, *Beyond Nagpur* — fleet TCO logic; ₹3.07/km fleet operating saving.

**Charging**
- SBI sector report, *E-mobility and charging infrastructure in India* (2026) — 29,151 public chargers (Dec 2025); 1–3% utilisation; 10–15% break-even.
- ev.care, *EV Fleet Depot Charging Setup in India: A 2026 Guide* — depot vs public tariffs; ToD; demand charges; charger:vehicle ratios.
- The Indian Express, 1 Sep 2026 — Green SM Limo Noida field evidence on charging downtime.

**Bio-CNG**
- PNGRB, *Compressed Biogas Integration in India's Gas Economy* (Aug 2025) — plant counts, blending mandate.
- PNGRB / Deloitte CBG session paper (2025–26) — 207 plants, 17 pipeline-connected, 20–60% utilisation.
- MoPNG PIB (Dec 2023) — CBG policy framework and blending schedule.

**Regulation**
- Delhi gazette SG.DEL-E.29112023-250308 — new-fleet onboarding schedule; full-fleet electrification by 1 April 2030.
- AIS-038 Rev.2 / AIS-156 — EV powertrain safety, thermal propagation, chemistry-change pathway.

**Battery-side** (from the verified battery report, not re-derived here)
- Naumann et al. 2018, *J. Energy Storage* 17, 153–169 — `10.1016/j.est.2018.01.019`
- Lewerenz et al. 2017, *J. Power Sources* 345, 2545 — `10.1016/j.jpowsour.2017.01.133`
- Eldesoky et al. 2022, *J. Electrochem. Soc.* 169, 100531 — `10.1149/1945-7111/ac99a6`
- Harlow et al. 2019, *J. Electrochem. Soc.* 166, A3031 — `10.1149/2.0981913jes`

---

## Appendix B — Assumptions used, and where each came from

| Assumption | Value | Source / status |
|---|---|---|
| Duty cycle | 200 km/day × 26 days × 12 | **Deck assumption.** Conflicts with the survey's 250–300 km/day (§9.3) |
| EV consumption | 12.84 kWh/100 km | Battery-phase verified duty; corrects the deck's 15.38 |
| Electricity | ₹8/unit | Deck assumption; depot off-peak is ₹5.50–9 |
| CNG price | ₹90/kg | Deck assumption |
| CNG mileage | 25 km/kg | Deck-implied. Sensitivity run 20–30 (§3.3) |
| EV on-road | ₹14,00,000 | Deck assumption |
| CNG on-road | ₹8,51,465 | Deck assumption (Dzire Tour S) |
| Residual (EV / CNG) | ₹5 L / ₹3 L | **Assumption — conservative on both.** A real fleet operator will have a view; flag this. |
| Fleet life | 5 years (loan) | Deck assumption; 312,000 km over the loan |
| Opportunity cost of charging | **zero** | **Only valid under return-to-base depot AC.** Not a general claim (§5.3) |

---

## Appendix C — Reproducing the numbers

Every figure in §3 and §4 is recomputable from the deck's own inputs:

```
duty:      200 km/day x 26 days = 5,200 km/mo ; 62,400 km/yr ; 312,000 km / 5 yr
EV energy: 312,000 x 12.84/100 = 40,061 kWh x Rs 8 = Rs 3,20,486
EV 5-yr:   14,00,000 + 3,20,486 + (1,200 x 60) + (3,500 x 60) = Rs 20,02,486 -> Rs 6.42/km
CNG energy:312,000 / 25 = 12,480 kg x Rs 90 = Rs 11,23,200
CNG 5-yr:   8,51,465 + 11,23,200 + (3,500 x 60) + (3,290 x 60) = Rs 23,82,065 -> Rs 7.63/km
range:      45 x 0.90 = 40.5 kWh / 0.1284 = 315 km
cycles:     200 x 0.1284 / 40.5 = 0.63/day x 312 = 198/yr -> 3000/198 = 15.2 yr
overnight:  36 kWh (10->90%) / 7.4 kW = 4.9 h ; / 11 kW = 3.3 h
```

Deck take-home check: 57,200 − (29,740 + 6,400 + 1,200 + 3,500) = **₹16,360** (deck prints ₹16,380).