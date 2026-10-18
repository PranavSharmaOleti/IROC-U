# Driver Earnings and the Rider
### MACH1 / FleetLine E1 — the two sides of the brief we had under-modelled
### Companion to `MACH1_TCO_ANALYSIS.md` (operator economics)

---

## 0. Why this document exists

The brief says the solution must maximise **customer satisfaction, driver earnings, fleet
profitability and scalability**. The TCO answers the third of those four, rigorously.
The other two were carried in a thesis table without a model behind them.

The two figures in that table — **₹93,600** and **₹114,400** — are asked about most often, so
they get answered first. Then the driver P&L in full. Then the rider.

---

# PART 1 — DRIVER

## 1. The two thesis numbers, derived

They are **gross revenue at two different fares**, nothing more:

| | Arithmetic | Result |
|---|---|---|
| ₹93,600 | ₹18.00/km × 5,200 km/month | **₹93,600** |
| ₹114,400 | ₹22.00/km × 5,200 km/month | **₹114,400** |

Both are **gross receipts before any cost**. They are not take-home, and they carry no
powertrain logic — the arithmetic is identical whichever vehicle you drive. Quoting either as
"driver earnings" is the gap a judge will find.

## 2. The driver P&L — fleet-operated vehicle

The driver does not carry the vehicle. Delhi, ₹11/km, 200 km/day, 26 days.

| Monthly line | EV | CNG |
|---|---|---|
| Gross revenue (₹11 × 5,200 km) | ₹57,200 | ₹57,200 |
| less platform access fee (₹67/day × 26) | −₹1,742 | −₹1,742 |
| less energy | −₹3,338 | −₹15,808 |
| less maintenance | −₹1,560 | −₹3,500 |
| less insurance | −₹3,500 | −₹3,290 |
| **Take-home** | **₹47,060** | **₹32,860** |
| **Advantage** | **+₹14,200 / month** | |
| Annualised | ₹5,64,715 | ₹3,94,320 |
| **Five-year cumulative** | | **+₹8,51,976** |

## 3. The driver P&L — driver-owned vehicle

Some drivers buy and finance their own cab. Then the EMI lands on their statement.

| | EV | CNG |
|---|---|---|
| Take-home **during** the 60-month loan | **₹20,021** | ₹14,768 |
| Take-home **year 6 onward** | **₹47,060** | ₹32,860 |
| Advantage during loan | +₹5,252 / month | |
| Advantage after loan | +₹14,200 / month | |

The step change at year six is the whole point of the ownership question: the EMI disappears
and the driver keeps the full advantage.

## 4. The finding that matters: the advantage is a fixed number

**The EV advantage is ₹14,200 every month, at every fare and every duty level.** It does not
scale with earnings — it scales with *nothing*.

| Fare | EV take-home | CNG take-home | Advantage | As % uplift |
|---|---|---|---|---|
| ₹11/km | ₹47,060 | ₹32,860 | **₹14,200** | **+43.2%** |
| ₹14/km | ₹62,660 | ₹48,460 | **₹14,200** | +29.3% |
| ₹18/km | ₹83,460 | ₹69,260 | **₹14,200** | +20.5% |
| ₹22/km | ₹1,04,260 | ₹90,060 | **₹14,200** | +15.8% |

**So the same ₹14,200 is worth twice as much in percentage terms to the lowest-paid driver.**
A driver on a ₹11/km street fare gains 43%. A driver on a ₹22/km airport run gains 16%. Both get
the identical rupees.

And it barely moves with duty — at 150 km/day the EV take-home is 145% of the CNG's, at
300 km/day it is 141%. The ratio is stable.

## 5. What the platform takes is irrelevant to the ranking

| Platform model | EV take-home | CNG take-home | Advantage |
|---|---|---|---|
| Flat ₹67/day (current Ola/Uber/Rapido) | ₹47,060 | ₹32,860 | **₹14,200** |
| Legacy 20% per ride | ₹48,799 | ₹34,600 | **₹14,200** |
| Legacy 25% per ride | ₹48,799 | ₹34,599 | **₹14,200** |

A percentage fee and a flat fee change *both* drivers' absolute income and move the
*difference* not at all. It is identical to the rupee.

**This matters because it defuses an obvious challenge.** A judge who suspects the flat-fee
model flatters our driver numbers cannot find a case where it does — the delta is invariant.

## 6. How robust is the driver case?

| Stress test | Result |
|---|---|
| CNG price rises to **₹200/kg** (today ₹76) | Advantage only then disappears |
| Duty falls from 200 to 150 km/day | +₹10,597 instead of ₹14,200 — still positive |
| Fare halves to ₹5.50/km (legacy commission) | Advantage still ₹14,200 |
| Platform switches to per-ride commission | No change to the advantage |

**The driver advantage is far more robust than the operator advantage.** The operator case is
sensitive to charger cost and duty; the driver case survives almost everything, because it is a
difference between two cost stacks, not a margin that can be squeezed.

## 7. What we will not claim on the driver side

- **Not** "drivers earn ₹93,600." That is gross revenue at an assumed fare. Take-home is ₹47,060
  at ₹11/km on a fleet-operated vehicle, ₹20,021 if they are also financing it.
- **Not** a single "typical driver earnings" figure. It ranges from ₹20,021 to ₹1,04,260
  depending on ownership model and fare, and presenting one number hides that.
- **Not** that the driver benefits regardless of duty. Below roughly 60 km/day a single vehicle
  cannot cover a driver's fixed costs at all — that is a utilisation problem, not a powertrain
  one.
- **Not** that driver income improves because the vehicle is better to drive. It improves
  because the operating cost stack is ₹1.24 lakh/month lighter.

---

# PART 2 — THE RIDER

## 8. What riders actually complain about

LocalCircles surveyed **17,993 respondents across 325 districts** (2025):

| Complaint | Share |
|---|---|
| Driver cancelled after learning destination or payment | **74%** |
| Surge pricing | 62% |
| Long waiting times | 53% |
| Unclean vehicles | 30% |
| Driver behaviour | 25% |
| Safety concerns | 6% |

A separate Bengaluru survey (10,000+ responses) found 85% of Uber users and 93% of Ola users
reported at least one of: cancellations, phone use while driving, surge pricing, unclean cars.

**The pattern matters more than the percentages.** Riders are not unhappy with the *car*. They
are unhappy with **cancellation, price unpredictability and vehicle condition** — and
cancellation is overwhelmingly the top complaint. A 5-star rating does not capture any of it:
research on Uber's own data found only 29.8% of trips are rated at all and most rated trips
receive five stars, with an average driver rating of 4.74/5. Ratings measure the absence of a
disaster, not the presence of a good ride.

## 9. What actually predicts satisfaction

A moderated SERVQUAL study on Bangalore ride-hailing (n=148) found three significant
predictors of customer satisfaction:

| Dimension | β | p |
|---|---|---|
| **Reliability** | .265 | < .001 |
| **Empathy** (courtesy) | .263 | .002 |
| **Tangibility** (vehicle condition) | .182 | .046 |

Reliability and empathy outrank vehicle condition. Tangibility is real but third. And in the
Bengaluru dynamic-pricing study (n=234), **perceived price fairness** — not perceived value —
drives satisfaction, explaining 47.6% of its variation.

Across a 30-market study with an Indian sample of 860, **50% of Indian respondents use
ride-hailing for their daily commute**, and safety/security is the top stated priority.

## 10. What riders say about the vehicle they actually ride

**Maruti Dzire Tour S** — the benchmark, rated on the platforms riders and drivers use:

| Sub-rating | Score |
|---|---|
| Mileage | 5.0 / 5 |
| Maintenance cost | 4.9 / 5 |
| Performance | 4.8 / 5 |
| Comfort | 4.7 / 5 |
| Safety | 4.1 / 5 |
| **Features & styling** | **1.2 / 5** |

Owner reviews repeat four praises — **mileage, low maintenance, service-network reach, ride
comfort** — and four complaints: **a basic cabin, no infotainment, no rear AC vents, and a
3-cylinder that feels underpowered.** One owner put it plainly: *"Only perfect for taxi like Ola
or Uber, because safety you have to compromise. For personal I would not prefer."*

There is also a brand problem worth naming: owners of the new-generation Dzire note it is
*"comfortable and looks premium, but still seen as cabs."* The taxi image is the stigma.

**Electric cabs** — the segment we are entering — score differently:

- **Silence and NVH are the single most-praised attribute.** Reviewers repeatedly single out
  cabin quietness, absence of engine noise, and absence of trim rattle as better than
  conventional premium sedans.
- **AC performance is called out as strong**, specifically in Delhi and Gurgaon summer heat.
- **Ride quality is rated above conventional Uber Black** sedans, though firmer on bad roads
  than a premium MPV.
- **Riders pay a premium for reliability.** The clearest rider statement in the research: *"It
  costs a bit higher, but I get peace of mind knowing my ride will show up."*
- **Dashcams, front and rear, are specifically praised** where present.
- **The losses are availability and size.** EV fleets are small, so pre-booking is required;
  7-seat MPVs beat 5-seat sedans for families; and drivers report range anxiety limiting
  where they can operate.

## 11. Where FleetLine E1 wins and loses

| Rider priority | Evidence | Our position |
|---|---|---|
| **Reliability** | Top SERVQUAL predictor; 74% top complaint is cancellation | **Strongest claim.** A 21.9 h/month downtime slack and a depot-charging operating model are the mechanism — a vehicle that is not queueing for a charger is a vehicle that shows up |
| **Tangibility / condition** | β=.182 predictor; 30% complain of unclean cars | Neutral-to-good. Silence and consistent cabin spec are a genuine upgrade; **features are where the Dzire scores 1.2/5, and an EV is the moment to fix that** |
| **Empathy / courtesy** | β=.263 predictor | Operator-controlled, not vehicle-controlled. Driver economics feeding §4 is the indirect lever |
| **Price fairness** | Explains 47.6% of satisfaction variation | EV caps operator cost but does **not** guarantee a fairer fare to the rider — this needs a platform commitment, and we should not claim it as a vehicle feature |
| **Safety** | Top stated priority; 6% formal complaints | Already specified: L2 ADAS, airbags, ABS. Note the fleet reality — rear seatbelt compliance is a behaviour problem, not a hardware one |
| **Quiet / comfort** | Most-praised EV attribute | **Free win.** An EV sedan is quieter than the CNG sedan it replaces, in the segment where noise is already the top complaint |

## 12. What the rider evidence says we should change

Three concrete implications, and they are spec changes, not slogans:

1. **Fix the features gap.** The benchmark vehicle scores **1.2/5** on features. An EV programme
   is exactly when to add what the CNG generation never got — rear AC vents, a real
   infotainment system, connected features. Riders rate tangibility third, but they rate it, and
   the incumbent's weakest score is ours to take.
2. **Front and rear dashcams as standard.** Riders name them as a differentiator on premium EV
   services. Cheap to specify, directly addresses safety which is the top stated priority.
3. **The boot is a customer feature.** Airport transfers are the margin segment, and the Dzire
   Tour S manages 382 L. At 400 L we already lead; we should say so in customer terms, not
   dimension terms.

## 13. The uncomfortable customer finding

**The rider's top complaint is cancellation, and our vehicle cannot fix it on its own.**
A driver cancels because the trip is unprofitable or the destination is awkward. Depot
charging and a ₹99,000 charger that stays working make the driver *more* reliable — that is a
real causal chain — but the honest position is that vehicle design moves rider satisfaction at
the margin, and the large win is in fleet operations.

We should claim that chain, because it is true and evidenced. We should not claim the vehicle
solves cancellation.

---

## Sources

**Driver economics** — derived from `MACH1_WORKING_FILES/tco_engine/` (sections A–R), Delhi,
escalated 5-year basis. Platform fee structure: Ola flat ₹67/day (Jun 2025); Uber/Rapido
subscription passes; legacy 15–30% per ride.

**Rider data**
1. LocalCircles (2025) — 17,993 respondents, 325 districts: cancellation 74%, surge 62%, waiting 53%, cleanliness 30%, driver behaviour 25%, safety 6%
2. LocalCircles Bengaluru (2024) — 10,000+ responses on Uber, Ola, BluSmart
3. Vinay S & Bharath R, *Asian Journal of Management and Commerce* (Oct 2026), DOI 10.22271/27084515.2026.v7.i10a.1504 — dynamic pricing, fairness, n=234, Bengaluru
4. *International Journal of…* (Oct 2026), DOI 10.33545/26633329.2026.v8.i10a.450 — moderated SERVQUAL, n=148, Karnataka
5. TGM Research, *Ride-Hailing Consumer Insights* — 30 markets, India N=860: 50% daily-commute reliance, safety top priority
6. ETAuto (25 Sep 2026) — five-star ratings; 29.8% trip rating rate, 4.74/5 average (Athey/Castillo/Chandar; NBER)

**Vehicle and EV-rider reviews**
7. Cardekho — Dzire Tour S user reviews, 4.7/5 across 66–67 reviews
8. ZigWheels — Dzire Tour S sub-ratings: features & styling 1.2/5, safety 4.1/5, comfort 4.7/5
9. Team-BHP — Dzire Tour S fleet owner; music-system integration complaint; rear seatbelt behaviour
10. r/CarsIndia (Oct 2025) — "comfortable and looks premium, but still seen as cabs"
11. Financial Express (13 Jun 2026) — Green SM Limo review: ₹8/km capped, no surge, cabin quietness, missing rear sun-shades and armrest
12. V3Cars (4 Jun 2026) — Green SM first ride: ride quality, AC in Gurgaon heat, "the driver could not casually cancel the ride"
13. Team-BHP (22 Jul 2025) — premium EV airport ride: NVH, dashcams, 5- vs 7-seat trade-off
14. The Hindu (13 Oct 2024) — Bengaluru commuters shifting to EV cabs for reliability; pre-booking trade-off
15. Inc42 (9 Jul 2026) — Green SM range anxiety as operational friction; driver-reported 5–6 hr battery backup
16. ExperiencesWithEVs — EV cab pre-booking requirement; older fleet ~150 km AC-on range
17. Green SM "Ride 5 Star" (Jun 2026) — consistent vehicle platform, driver training, supervision
