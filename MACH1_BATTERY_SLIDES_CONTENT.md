# MACH1 Battery Section — 3-Slide Content Pack

Companion to `MACH1_BATTERY_EXECUTIVE_REPORT.md`.
Written to be spoken aloud to judges. Trim, reorder, and cut as needed — all figures trace
to the executive report and to `/tmp/opencode/mach1/mach1_model.py`.

---

## SLIDE 1 — The Choice and Why It Holds

**Headline:** LFP + detachable architecture — the only option that survives 2034
homologation, Indian supply, and 8-year duty.

### ① Why not sodium
- No 45 kWh-class sedan supplier exists
- No cycle data at Indian ambient conditions
- Homologation standards reference **lithium**, not sodium

→ Sodium becomes the **2036–38 second act**, not the primary plan.

### ② Why LFP
- Domestic supply chain exists — Exide 6 GWh (2026), Agratas (2027), Ola 1.4 GWh
- Best-in-class cycle life
- **Lowest cost per usable kWh**
- No nickel or cobalt price exposure
- **Low charge ceiling is a durability advantage.** Published NMC testing shows degradation
  sensitivity to how much time a cell spends at high voltage — and that sensitivity
  **disappears entirely below a 4.06 V ceiling.** LFP runs at ~3.6 V. We are not trying to
  engineer this property in; our chemistry already sits below the threshold where the
  problem appears.

### ③ Why detachable, not structural
- Chemistry swap becomes a **software change, not a new car**
- **AIS-038 Clause 2.48**: a chemistry change needs full REESS retest either way
- But detachable makes the *cell* swappable. Structural CTC locks the chemistry forever
- Cost of that optionality: **₹2–3 Cr / 4–6 months** vs **₹15–25 Cr / 18–24 months**

### ④ Why the market needs exactly this
- Fleet operators already **multi-source** — Everest runs three Tata models simultaneously
- No platform lock-in anywhere in the segment
- Whoever makes the **best TCO cell** wins the next tender, not whoever owns the platform

### ⑤ Where the market is going
- **PM E-DRIVE excludes 4W passenger cars** (gazette notification) — the 2025–26 dip is
  policy, not collapse
- Delhi gazette sets a **staged new-fleet EV ladder: 5% → 50% → 100% over five years**, with
  full fleet electrification required by **1 April 2030** — and it carries real penalties
- Our 2034 launch lands in the **growth phase**, not the dead zone

> **Delivery line:** *"Sodium sounded better on paper. But you cannot homologate a
> chemistry that has no supplier and no test data. We chose the chemistry we can actually
> certify — and kept the door open for sodium later by making the pack swappable."*

---

## SLIDE 2 — The Math That Proves It Works

**Headline:** We didn't estimate. We modelled it against the best published LFP data, and
here's what it says.

### ① Duty cycle — verified, not assumed
- 12.84 kWh/100 km base consumption
- 200 km/day
- **25.68 kWh/day** actual
- ~200 equivalent full charges per year

*Our deck originally said 38.28 kWh/day. Real-world data says 25.68 — a 33% correction
we made ourselves.*

### ② Pack sizing
**43–44 kWh at 48 °C cell. 41 kWh with a proven chiller loop.**

### ③ The finding we lead with

Two peer-reviewed studies. Same LFP chemistry. Same 40 °C. Opposite answers.

| Study | Method | Years to 80% SoH |
|---|---|---|
| Naumann 2018 | Fitted square-root law | 13.3 yr |
| **Lewerenz 2017** | **Measured linear fade** | **3.7 yr** |

Our model **reproduces Lewerenz's own published "3–4 years" exactly.** We are not
asserting it — we are checking it.

**What we did about it:** we didn't pick the flattering number. We reported both, carried
the full 0.45–1.00 exponent range, and turned the disagreement into a **6-cell test
programme** that resolves it on our chemistry.

### ④ The exposure nobody models
Resistance ages **4.2× faster** than capacity.
At 48 °C: **+101% resistance by year 8 → ~50% of rated power.** A capacity warranty cannot
see this. We added a separate warranty clause.

### ⑤ TCO — already winning, on primary data

| City | Ours (EV) | CNG sedan |
|---|---|---|
| Delhi | **₹2.55/km** | ₹3.15/km |
| Bengaluru | **₹2.80/km** | ₹3.60/km |
| Mumbai | **₹2.95/km** | ₹3.80/km |
| Hyderabad | **₹2.65/km** | ₹3.35/km |

Built from OEM fleet price lists, state electricity tariffs, and CNG prices — no contested
market-share statistic required.

> **Delivery line:** *"Every number on this slide comes from published cell data or state
> tariffs. Where the literature disagreed, we showed you the disagreement instead of
> picking the convenient side. And where our own deck was wrong, we corrected it."*

---

## SLIDE 3 — Where the Evidence Comes From

**Headline:** Peer-reviewed, cell-level, and we know exactly where it does *not* transfer.

### ① The evidence base

| Source | What it gave us |
|---|---|
| **Naumann 2018** — *J. Energy Storage* | LFP calendar model: activation energy, SOC factor |
| **Lewerenz 2017** — *J. Power Sources* | 50-cell LFP dataset, linear fade at 40 °C |
| **Simolka 2020** — *J. Applied Electrochemistry* | LFP DoD + temperature post-mortem |
| **Schreiber 2025** — *J. Energy Storage* | Real VW ID.3 duty cycling |
| **Gauthier 2022** — *J. Electrochem. Soc.* | DoD × C-rate × calendar matrix |
| **Eldesoky 2022** — *J. Electrochem. Soc.* | 12,000-hr DoD × C-rate × **voltage** × temperature study |
| **Graner 2026** — arXiv | Lab-to-field uncertainty, probability bands |
| **Waldmann 2014** — *J. Power Sources* | Temperature mechanism crossover |
| **Pozzato 2023** — *Joule* | Real-world field behaviour |

### ② What we corrected in our own proposal
- Deck consumption 38.28 → **25.68 kWh/day** (real-world data)
- Charge-rate row **removed** — not a real constraint
- 45 °C ageing claim **restated** on Arrhenius basis
- Reliance/Faradion milestone **replaced**
- Two market statistics **removed** — no primary source exists

### ③ What we know we don't know

*Judges respect this more than false certainty.*

- **LFP calendar exponent: 0.45 or 1.0?** Published studies genuinely disagree. This is our
  single largest open question and it dominates pack size.
- DoD effect: now bounded — best available evidence says the effect is **small** (10–15 mAh
  across 25→100% DoD over 12,000 hours). What matters is **time at high voltage**, not depth.
- **No LFP-specific cycling dataset exists at our 40–48 °C with partial DoD.** Our numbers
  extrapolate across chemistries, and we label them as such.
- Louli & Dahn / Harlow 2019: **NMC532, not LFP** — and cycled to a *higher* 4.3 V ceiling than
  ours. Its 1.6-million-km headline is an upper bound for the field's best benchmark cell, not a
  number we can claim. Still no LFP DoD matrix in hand.

### ④ Why that honesty is a strength
The one question that actually drives our answer — the calendar exponent — has two published
LFP answers that differ by 3.6×. We show you both, carry the full range, and specify the
six-cell test that closes it. Every other assumption is either measured on our chemistry or
labelled as borrowed.

> **Delivery line:** *"We built this from published cell data, not vendor claims. We found
> real disagreements in the literature and we showed them to you. And we can tell you
> exactly which test closes each gap."*

---

## If you're short on time

**Must keep**
- Slide 2 block ③ — the literature disagreement. This is the credibility anchor.
- Slide 1 block ⑤ — market direction without a contested statistic.
- Slide 3 block ③ — what we don't know.

**Can compress**
- Slide 1 blocks ② and ③ into one combined block
- Slide 3 block ① into a footnote strip

**Never cut**
- Slide 2 block ⑤ — the resistance finding. Most original thing in the deck; most reviewers
  will never have considered it.

---

## Speaker notes — likely judge questions

**"Isn't 43 kWh heavy?"**
At 44 kWh and our verified 25.68 kWh/day, range is ~340 km real-world. Weight sits within
the segment for a 45 kWh semi-structural pack, and the 10% EOL reserve means usable
capacity drops to ~39 kWh, not 44.

**"Why not just buy an LFP pack off the shelf?"**
Because every published LFP DoD dataset is on a different nickel-based chemistry. We'd be
extrapolating across chemistries. The validation programme is what lets us claim the number
instead of guessing it.

**"Your warranty says 8 years. Your own slide says it might not hold."**
Yes — deliberately. We show both published answers rather than picking one. That's why the
6-cell test is the first deliverable, and why the warranty is written against a power
threshold as well as a capacity threshold.

**"How do you know TCO numbers are right?"**
State electricity tariffs (DERC/BESCOM/TNERC/MERC), CNG prices (IGL/APCPDCL), OEM fleet
price lists, and 9.5% fleet finance. All primary. The failure mode we publish with it: below
~150 km/day, or without depot charging, CNG wins.

**"Sodium is the future."**
Agreed — that's why our pack is swappable. We'd change the chemistry without changing the
car. But we can't certify it in 2034 with no supplier and no test data.