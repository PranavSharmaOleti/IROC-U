# MACH1 / FleetLine E1
## Who we build for — and why

---

> ### The buyer is a fleet operator, not a driver.
>
> Driver economics improve **because** the operator's do. Every commercial conversation
> about a fleet vehicle ends at an operations manager's desk — and that person buys on
> cost per kilometre and utilisation, not on take-home pay.
>
> **Structurally, drivers now choose the platform; operators choose the vehicle.**

---

## 1. Who the buyer is

Our buyer is the fleet operator running 5,000–40,000 vehicles in Indian metros — Ola and
Uber, Refex, Everest, Lithium Urban, and the airport-specialist entrants that refilled the
gap when BluSmart exited: Evera across Delhi terminals, GMR Hyderabad's 200-plus vehicle
premium airport fleet, and Bharat Taxi at Navi Mumbai.

| | |
|:---|---:|
| **40,000–50,000** | ride-hailing vehicles in our addressable metros |
| **8,000–10,000** | of those already electric |
| **1** | replacement window now open |

*India has roughly 40,000–50,000 ride-hailing vehicles in our addressable metros, of which
about 8,000–10,000 are already electric. The operator has already started replacing.
This is the replacement window.*

---

## 2. Why this audience for this competition

Because this competition is about the **high-utilisation fleet duty cycle** — a narrow,
measurable segment. We deliberately did not try to serve the largest one.

| | **VOLUME sits here** | **MARGIN sits here** |
|:---|:---|:---|
| **Use case** | Street-hail intra-city | Airport + corporate commute |
| **Share of rides** | ~58% | ~19% combined |
| **Paid km/day** | ~95 | **144–210** |
| **Dispatch** | unpredictable | **pre-booked** |
| **Price sensitivity** | 0.85 | **0.30–0.35** |
| **EV adoption today** | 10% | **18%** |

> ### Under India's new flat-fee platform economics — Ola at ₹67 per vehicle per day,
> ### Uber and Rapido at ₹29 — revenue per vehicle is **fixed**.
> ### The only variable left is **paid kilometres per day**.
> ### Utilisation, not fare, decides the economics now.

Those two segments **require different vehicles**. A vehicle engineered for the margin
segment is structurally wrong for the volume segment — the duty cycle, the charging access
and the economics do not transfer.

So we specified for the margin segment, **and said out loud that we are not claiming the
volume segment.**

---

## 3. What actually matters to them, in order

| Rank | Criterion | Why |
|:--:|:---|:---|
| **1** | **Cost per kilometre, all-in** | Every credible fleet TCO study converges here |
| **2** | **Paid km/day** | The binding constraint under flat-fee economics |
| **3** | **Uptime** | Charging downtime is the failure they actually fear |
| **4** | **Depot control** | Without controlled overnight charging, the electric case does not close |
| **5** | **Residual value** | BluSmart assumed 10% and realised 26% — our exact segment published their own number |
| **6** | **Financeability** | Financing structure alone is worth about 8 points of advantage |
| **7** | **Range** | **Last.** 315 km against a 200 km/day duty is ample |

*Rank 7 is a deliberate point, not a forgotten one.*

---

## 4. Two things that cut against the usual pitch

> **Range is not a decision driver for this buyer.**
> It sits at the bottom of the list. If your deck leads with range, it is leading with the
> wrong number.

> **The buyer's fear is downtime, not range.**
> An operator cannot send a driver home if the vehicle is charging when it should be
> earning. That is why our specification leans on depot control, and why **per-cell
> State-of-Health telemetry is specified rather than optional** — it is the mechanism that
> makes an eight-year capacity-retention guarantee credible at all, given published LFP
> studies disagree **3.6×** on time-to-80%.

---

*Every figure here traces to the market assessment (`MACH1_MARKET_ASSESSMENT.md`) and the
TCO analysis (`MACH1_TCO_ANALYSIS.md`). Full source list in those documents.*

---

> **On framing.** *"Why this audience"* is strongest when it admits a limit rather than
> claiming the whole market. Saying we measured intra-city, that it was 58% of the volume,
> and that it is the wrong vehicle for this design — that is a stronger position than
> claiming everything. And it is much harder for a judge to argue with, because the
> reasoning is visible.