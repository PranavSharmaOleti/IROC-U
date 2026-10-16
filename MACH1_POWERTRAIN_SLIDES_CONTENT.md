# MACH1 / FleetLine E1 — Powertrain & Technical Specs
### Slide content pack · Items 3 & 4 · jury-facing

---

## SLIDE 1 — POWERTRAIN & ENERGY STRATEGY

### ① The choice, and why it is not close
**BEV. LFP. Single-speed reduction drive.**

> "For taxis, high annual mileage makes EVs the most cost-effective option, followed by CNG where infrastructure exists."
> — CEEW, cost-of-ownership study

**One qualifier earns the whole answer:** our duty cycle is **200 km/day returning to a depot**.
That is the single most favourable operating profile in the Indian market.

### ② Why 200 km/day decides it
- Fleet TCO parity with diesel emerges at **120–200 km/day**; payback in **18–24 months**
- Return-to-base parity can start at **100–150 km/day**
- **Our duty sits at the top of that band** — the margin is widest exactly where we operate
- *The Hindu BusinessLine, Feb 2026 — EKA Mobility, Euler Motors*

### ③ The number that actually matters: cost per km
**Operator cost, 5 years, 312,000 km**

| | EV | CNG |
|---|---|---|
| Cost/km | **₹6.42** | ₹7.63 |
| Less residual | **₹4.82** | ₹6.67 |
| Advantage | **16% / 28%** | — |

**Robust to the fuel-economy assumption:**

| CNG mileage | 20 km/kg | 25 km/kg | 30 km/kg |
|---|---|---|---|
| CNG cost/km | ₹8.34 | ₹7.63 | ₹7.42 |
| EV advantage | **23%** | **16%** | **13%** |

> "Higher kilometers traveled equates to better relative TCO of the EV option."
> — Cadmus / Uber, *Electrifying Ridehail in India*, Jan 2026

### ④ Why charging is the *enabler*, not the objection
- **36 kWh overnight (10→90%) = 4.9 h at 7.4 kW · 3.3 h at 11 kW** → done before the shift
- **Zero revenue-hours lost to charging.** No queue, no offline, no missed target.
- Depot off-peak **₹5.50–9/kWh** vs public fast charge **₹18–24/kWh**
- Smart off-peak scheduling cuts charging cost **20–35%**; **1:3 charger-to-vehicle** is achievable

### ⑤ Where we are not claiming
- **Zero tailpipe — not zero emission.** India's grid is ~75% coal.
- CNG has better refuelling readiness. It is our **named fallback** if depot charging fails.
- EV's cost advantage is **geography-dependent** — it leads where charging exists.

---

## SLIDE 2 — TECHNICAL SPECIFICATIONS

### ① Range and energy
- **45 kWh LFP** · 10–90% usable (36 kWh) · **263 km claim** — conservative
- **Verified consumption 12.84 kWh/100 km → real range ~315 km**
- **25.7 kWh/day** at 200 km/day · **0.63 cycles/day**
- Daily charge: **~36 kWh · 3.3 h at 11 kW overnight**

### ② Battery & energy system
- **PMSM, 80 bhp continuous / 100 bhp peak**, water-cooled
- **Single-speed reduction drive** · peak efficiency **93–97%** · ~2% loss at 45 °C
- **Active liquid-cooled pack**, held ≤45 °C
- **1–2C peak charge** (45 kW at 1C) · **overnight AC at 11 kW**
- Chemistry locked to **LFP** — no dependence on unproven sodium chemistry

### ③ Safety
- Airbags · ABS · **ESC** · Level 2 ADAS
- **AIS-156** thermal propagation · **AIS-038 Rev.2** EV powertrain safety
- **Microprocessor BMS** with cell-level voltage and temperature monitoring
- 72-hour edge buffer — critical safety events handled on-vehicle, not via cloud

### ④ Durability for commercial duty
- 62,400 km/yr · **312,000 km over the loan**
- **Drive unit 200,000+ km** rated — *3.2 years at our duty; replacement planned, not assumed away*
- **Battery first life ~15 years** (198 cycles/yr, not 365)
- **Service interval in months, not kilometres** — high-km vehicles otherwise over-serve worn parts
- Corrosion and vibration validated for monsoon and coastal duty

### ⑤ Comfort, interior and luggage
- **5-seat, 2-row, rear-biased** — paying passengers sit where it is roomiest
- **Flat floor, no tunnel** — EV architecture advantage
- **Rear AC vents** · ventilated seats · durable leatherette
- **400 L boot** — separate, unobstructed, matches airport-transfer demand

---

## SLIDE 3 — WHY WE CHOSE IT

### ① The alternatives, and why each loses
| Option | Why not |
|---|---|
| **CNG** | Winner on refuelling readiness. **Loses on cost at our duty** — the capital premium takes ~5 years to repay. **Our fallback.** |
| **Bio-CNG** | Best carbon story of any fuel. **Not deliverable:** 207 plants live vs a 5,000 target; only **17 pipeline-connected**; plants running at 20–60% capacity. |
| **HEV** | **Taxed out at 43% GST + cess.** Also inherits the full ICE service burden while adding a battery. |
| **PHEV** | Same, plus two powertrains to service and two failure modes to train. |
| **Mix** | Our customer runs **one fleet, one service network, one training pipeline.** Maruti's edge *is* that single ecosystem. |

### ② Sustainability — the honest version
- **Zero tailpipe emissions** in Delhi NCR, where air quality is the binding constraint and mandates are already gazetted
- **~50–60% below petrol** well-to-wheel today — improves as the grid cleans
- **A depot fleet can decarbonise its own electricity.** A gas fleet buys whatever the pipeline has.
- Bio-CNG would be lower-carbon still — which is why it stays on the watch list for post-2035

### ③ What we know we don't know
- **LFP calendar ageing at 40 °C is genuinely contested** — two peer-reviewed studies differ by **3.6×** on time-to-80%. We carry the full range rather than pick one.
- **Charging geography, not chemistry, drives regional adoption.** EV taxis lead where hubs exist.
- **Our duty assumption is the load-bearing input.** At 300 km/day a 45 kWh pack does not close the day — and we have sized for 200.

### ④ Why that honesty wins
Every number here is either measured on our duty cycle, taken from a named source, or labelled as
an assumption. The pack sizing, the cost model and the charging plan all trace to one stated
duty cycle — **200 km/day, return to base** — and we show what breaks if that number is wrong.

---

## TRIM TRIAGE (if you need to cut)

**Cut first — least load-bearing:**
- Slide 3 ② sustainability bullets 3–4 (keep the tailpipe claim, drop the CNG methane detail if short)
- Slide 1 ⑤ "where we are not claiming" — retain only if there is room for a caveat slide
- Slide 2 ④ corrosion/vibration line

**Never cut:**
- Slide 1 ③ the cost-per-km table — it is the argument
- Slide 1 ④ the overnight-charging feasibility — it is the condition
- Slide 3 ① the alternatives table — "choose among BEV/HEV/PHEV/CNG/Bio-CNG" is an explicit ask
- Slide 3 ③ the contested-parameter line — it is the credibility anchor

---

## SPEAKER NOTES — five questions you will be asked

**Q1. "Why not CNG? It's cheaper to buy and refuelling is everywhere."**
> Refuelling readiness is CNG's genuine win — I won't argue otherwise. But our duty is 200 km/day,
> which is exactly where the economics flip: EV wins 16–28% on cost per kilometre over five years,
> and it wins across every plausible CNG fuel-economy assumption. CNG becomes the fallback, not
> the answer, once depot charging is in place.

**Q2. "What happens when a charger is down?"**
> That's the wrong question for our operating model, and it's the right question for the
> public-charging fleet that failed in Noida. We charge at our own depot overnight. Three and a
> third hours at 11 kW, done before the shift starts. Zero revenue-hours exposed. We also carry
> CNG as a named fallback.

**Q3. "Is 45 kWh enough?"**
> Comfortably, and we are being conservative. Our claim is 263 km. On the verified duty cycle the
> same pack gives about 315 km. It covers our 200 km/day with margin. I should be clear that this
> holds at 200 km/day — at 300 km/day we would need roughly 51 kWh, and we have sized for the
> duty we actually run.

**Q4. "Why not Na-ion, or hybrids?"**
> Hybrids are taxed into uncompetitiveness at 43% GST plus cess, and they keep the entire ICE
> service burden while adding a battery. Na-ion we assessed seriously: it's blocked by an
> Indian certification standard that names lithium chemistry, not by cost. LFP is commercial,
> proven, and available now. We'd rather ship the chemistry that exists.

**Q5. "Your battery warranty claim?"**
> We separate first life from warranty, deliberately. First life on our duty cycle is roughly
> 15 years. The warranty is a smaller and less certain number, because two peer-reviewed LFP
> studies disagree by 3.6× on time-to-80% at 40 °C. We carry both, and we run a six-cell
> validation programme to close it. I'd rather show you the spread than pick the flattering end.

---

## CORRECTIONS TO THE EXISTING DECK

| # | Issue | Fix |
|---|---|---|
| 1 | Table headed **"Total Cost of Ownership"** actually contains driver net take-home — higher is better | Relabel; add a separate operator cost/km table |
| 2 | EV take-home printed **₹16,380**; inputs give **₹16,360** | Correct to 16,360 |
| 3 | Consumption stated as 15.38 kWh/100 km in places, 12.84 in others | Use 12.84 as primary, state basis |
| 4 | Duty cycle **200 km/day** (deck) vs **250–300 km/day** (survey) | Pick one; we recommend 200 + return-to-base |
| 5 | Cycles/year stated as **365**; actual at our duty is **~198** | Correct — pack life is ~15 yr, not 8.2 |
| 6 | Boot **400 L** in spec table, **420 L** in graphic | One number only |
| 7 | **ESC absent** from safety spec | Add ESC |
| 8 | **Pack thermal management not specified** | Add active liquid cooling, pack ≤45 °C |
| 9 | HVAC line items sum to **14.80 kWh/day** vs 12.84 verified duty | Reconcile and state AC load explicitly |
| 10 | No statement of the operating premise | Add: return-to-base, overnight depot AC charging |