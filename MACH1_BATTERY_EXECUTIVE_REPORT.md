# MACH1 / FleetLine E1 — Battery Section Executive Report

**Prepared for:** competition jury review
**Date:** 16 October 2026
**Status:** Final conclusions from full literature audit, primary-source market
verification, and an independently audited lifecycle model
**Companion:** `MACH1_BATTERY_SLIDES_CONTENT.md`

---

## 0. The one-paragraph version

We chose **LFP over sodium-ion** because three independent walls — no 45 kWh-class
supplier, no cycle data at Indian ambient, and Indian homologation standards that name
*lithium* in the title — each independently block certification before the 2034–35
launch window. None of those walls is about cost. We chose **LFP with a detachable pack
architecture** so the chemistry stays swappable and sodium remains a genuine 2036–38 option
rather than a written-off bet. On sizing, the honest answer is a **range, not a number:
40.6–74.6 kWh** depending on two things published LFP data cannot resolve. The decisive
finding of this work is that **cell temperature, not pack size, determines whether the
8-year warranty holds** — and we can demonstrate it with arithmetic on peer-reviewed LFP
data rather than assertion. That reframes the deliverable from *"a pack"* to *"a thermal
architecture plus a costed validation programme."*

---

## 1. Chemistry selection

### 1.1 The original proposal's thesis, stated fairly

The MACH1 deck (`MACH1_NITDURGAPUR.pdf`) proposes:

> *"architecture designed around Na-Ion Battery. The car targets 2035, We have enough runway
> for Na-Ion to close the cost gap and mature"*
>
> *"Na-Ion commercially finalised around Na-Ion primary cell"* … *"Na-Ion as primary
> offering, LFP as [fallback]"*

The survey document already hedges: *"We will consider battery pack, LFP type. Predict
Na-ion to reach LFP price range in 5 yrs after"*.

**This is not a naive claim, and it deserves a fair hearing.** Sodium-ion's cost trajectory
is real, and layered-oxide sodium cells genuinely do reach LFP price parity on a
five-year view. The instinct — *"we launch in 2035, so wait for the better chemistry"* — is
commercially reasonable.

It fails on **timing and certification**, not on direction.

### 1.2 Why 2035 does not solve it — three independent walls

Each of these must clear. Any one of them failing kills the primary-chemistry plan.

**Wall 1 — The cell does not exist at our scale.**
No supplier ships layered-oxide sodium-ion in a sedan-class vehicle. Current automotive
deployments are **A00-segment microcars at 23–25 kWh** (HiNa in the JAC Yiwei 3, Farasis in
the JMEV EV3). The one sodium-ion product with GWh capacity *and* a passenger car *and*
GB 38031-2025 certification is CATL Naxtra — and it is **Prussian White**, a different
cathode family from the layered oxide the proposal specifies. Prussian White is not a
drop-in substitute for the specified chemistry.

**Wall 2 — The data does not exist.**
There is **zero cycle-life data for any layered-oxide sodium cell at 60–80% DoD *and*
40–45 °C.** Every public headline claim has undisclosed DoD, undisclosed temperature, or
both. RWTH tested commercial layered-oxide cells to 45 °C but only for *calendar* ageing;
TUM found severe 45 °C degradation at high SOC, again without cycling. By contrast LFP has
published, citable data: **4,000 cycles at 25 °C, 2,000 at 45 °C** (WRI). We cannot build a
defensible comparison when one side has no number at all.

**Wall 3 — It cannot be legally homologated in India.**
AIS-038 Rev.2 Amendment 3, Annex IX-K(2), verbatim:

> *"Cells used to make REESS, shall be certified as per IS 16893-Part 2 and Part 3 by NABL
> accredited lab or by test agency notified under CMV Rule 126."*

IS 16893-2 and -3 are titled *"Secondary **Lithium-Ion** Cells…"*. No amendment through Amd 4
has added an alternative-chemistry clause or scope exemption. No sodium-ion cell has ever
been certified to them.

**There is no import workaround.** Importing a finished pack does not help, because the pack
itself must be type-approved under AIS-038, which in turn requires the cell certification.

**A year of additional runway does not move Wall 3.** That clause names lithium in the
standard's own title. It is a standards question, not a maturity question. Waiting does not
fix it — only a standards amendment does.

**Joint probability of all three walls clearing by January 2034: under 10%.**

### 1.3 The duty and tariff detail that cuts *against* sodium

| Item | Position | Effect on sodium |
|---|---|---|
| HSN 8507.60 | *"Lithium-ion accumulators"* only | Na-ion falls under **8507.80 "Other accumulators"** → **15% BCD** vs 20% |
| 5% concessional BCD | Operative text: *"for **Lithium-Ion** Cells for batteries of EVs or BESS"* | **Excludes sodium** |
| 0% capital-goods BCD | *"for **Lithium Ion Cell** manufacturing"* | **Excludes sodium** |
| GST | Uniform **18%** across heading 8507 post-GST-2.0; PIB explicitly names sodium in the 28%→18% cut | Neutral |

Net effect: sodium gets a marginally lower headline duty (15% vs 20%) but **loses every
concession**, and GST is neutral. **There is no duty advantage either way.** The lower
headline number is misleading unless stated alongside the lost concessions.

### 1.4 Decision

**LFP is the primary chemistry. Sodium-ion is a documented 2036–38 second act** — retained
precisely because the architecture keeps it available. We are not arguing sodium-ion is the
wrong direction. We are arguing it cannot be *certified* on the proposed date, and a
programme that cannot be certified cannot be delivered.

---

## 2. Architecture — why detachable, not structural

**Semi-structural CTP · standard prismatic envelope · chemistry-specific firmware · common
BMS hardware.**

| Dimension | Detached semi-structural CTP | Full structural CTC |
|---|---|---|
| Chemistry change | Cell swap + firmware | Effectively impossible |
| AIS-038 Clause 2.48 retest | 4–6 months, ₹2–3 Cr | 18–24 months, ₹15–25 Cr |
| Cell standardisation | 256×106×32 mm prismatic, 102–108 s | Chemistry-locked |
| Repurposing / second life | Straightforward | Very difficult |
| Body programme impact | None | Full body-in-white retool |

**The argument in one line:** Clause 2.48 requires a full REESS retest on *any* chemistry
change. That cost is unavoidable. The architectural question is only whether the *cell* stays
swappable afterwards. Detachable says yes; structural says never.

This also creates a **residual-value argument** for judges: a buyer can upgrade cells
without buying a new car.

---

## 3. Market analysis

### 3.1 Two claims we removed, and why

| Removed claim | Finding |
|---|---|
| Xpres-T fleet share **89% → 53%** | Tata press releases return 403. ET, Autocar Pro and Financial Express all redirect to an unrelated article. **No Vahan or SIAM corroboration exists.** Tata's FY24 annual report does not disclose fleet-EV share. The definition is ambiguous — 89% of *fleet EV registrations*, *all EV passenger cars*, or *Tata's own fleet EV sales*? Unknowable |
| Fleet orders **26,000 → 2,000** (−92%) | The cited Financial Express article **does not exist.** Every URL ending `3400000` redirects to a PM Modi tribute article. Wayback Machine has no capture. **Zero corroboration** from SIAM, Vahan, Redseer, ICCT, Jefferies or Crisil |

**This is not fixable with more digging.** Indian fleet-EV share is not reliably measurable
from public data: Vahan aggregates by category (M1, taxi, maxi-cab) and never provides an
OEM- or model-level fleet/private split; fleet-versus-private classification is inconsistent
across states; retro-fit and grey-market registrations go uncounted. JMK, IEA and SIAM all
derive from the **same Vahan feed** — they are one source dressed as three.

### 3.2 What we can defend instead

**TCO parity already exists.** Built entirely from primary sources — OEM fleet price lists
(2025), state electricity tariffs (DERC/BESCOM/TNERC/MERC), CNG prices (IGL/Mahanagar Gas/
APCPDCL), 9.5% fleet finance rate, 4-year / 1.2 lakh km, 300 km/day utilisation with depot
charging:

| City | 45 kWh EV sedan | CNG sedan | Advantage |
|---|---|---|---|
| Delhi | **₹2.55/km** | ₹3.15/km | −19% |
| Bengaluru | **₹2.80/km** | ₹3.60/km | −22% |
| Mumbai | **₹2.95/km** | ₹3.80/km | −22% |
| Hyderabad | **₹2.65/km** | ₹3.35/km | −21% |

**Published failure mode:** below ~150 km/day utilisation, or without depot charging, CNG
wins. We state this alongside the table — a TCO claim without its boundary condition is not
a claim.

**The 2025–26 dip has a documented cause that needs no fabricated statistic.**

| Scheme | 4W passenger coverage | Fleet eligible |
|---|---|---|
| FAME II (ended 31 Mar 2024) | ✅ ₹10,000/kWh, capped at **20% of vehicle cost**; vehicle price must be <₹15 lakh | ✅ |
| **PM E-DRIVE** (from 29 Sep 2024, **extended to 31 Mar 2028**) | ❌ **4W passenger cars excluded** | ❌ |
| PM E-DRIVE scope | e-2W, e-3W (e-rickshaws/e-carts, L5), e-ambulance, e-truck only | — |

*Correction: FAME II's ₹1.5 lakh figure was **not** the 4W cap — that is the e-2W *price
threshold*. The 4W cap is 20% of ex-factory cost, and NAB records actual e-Verito payouts of
₹1.59–2.12 lakh.*

The fleet-EV slowdown tracks a subsidy cliff and an explicit policy exclusion. That is a
better explanation than a 92% collapse, and it is verifiable from the gazette.

**Mandates are real and gazetted.** The Delhi Motor Vehicle Aggregator and Delivery Service
Provider Scheme, 2023 (gazette SG.DEL-E.29112023-250308) sets **new-fleet onboarding rates**,
not a total-fleet conversion deadline:

| Four-wheeler | 6 mo | 1 yr | 2 yr | 3 yr | 4 yr | 5 yr |
|---|---|---|---|---|---|---|
| **EV share of new fleet onboarded** | 5% | 15% | 25% | 50% | 75% | **100%** |

Separately, every aggregator and delivery fleet must be **fully electric by 1 April 2030**.
The scheme **does carry penalties** — Chapter V permits licence suspension or cancellation for
non-compliance — so this is an enforced ladder, not an aspiration.

*Correction: an earlier draft of this document cited these as "5% by 2025, 25% by 2027, 100%
by 2030". Those percentages were right but attached to the wrong years; the schedule above is
the gazette's actual milestone structure.*

**The real buyer base is small, verifiable, and multi-sourced.**

| Operator | Total fleet | EV fleet | EV % | Source |
|---|---|---|---|---|
| Everest Fleet | **22,000+** | ~2,000 | ~9% | ICRA rating rationale, 31 Dec 2025 |
| Lithium Urban | 3,000+ | 3,000+ | ~100% | Company disclosure |
| BluSmart | — | — | — | **Defunct** — operations collapsed 2025 |
| Mahindra Logistics (Meru→Alyte) | asset-light, not disclosed | not disclosed | — | Asset-light; fleet is largely driver-owned |
| Ola / Uber | platforms, not owners | Not disclosed | — | — |

*Corrections: Everest's own website still says 18,500 vehicles / 2,000+ EV; the ICRA rating
rationale gives **22,000+ as of 31 Dec 2025**, which we use as the current figure. BluSmart is
not merely "paused" — it is **defunct**. The previously cited "50,000+ deployed / ~500 EV" for
Mahindra Logistics could not be sourced and has been removed; the company runs an asset-light
model and does not publish EV counts.*

Addressable owned/managed fleet base is therefore **order-of-magnitude 40,000–50,000 vehicles,
with roughly 8,000–10,000 electric**. Growth since 2023 has come from dedicated EV fleetcos
rather than aggregator conversion — the direction that matters for us.

**Multi-sourcing is the norm.** Everest runs Tigor EV, Xpres-T and Nexon EV simultaneously.
Meru specifies e-Verito, Tigor, Nexon and MG ZS. State tenders (KSRTC, MTC, DTC) specify
technical parameters, not OEM. **There are no platform lock-ins.** Whoever delivers the best
TCO wins the next tender.

**Competitive outlook.** Maruti Suzuki has no fleet-EV programme. The eVX is a **60 kWh
private SUV positioned as a global export flagship** (Europe and Japan), with published price
estimates spanning **₹18–25 lakh** depending on source and variant. That sits decisively
above the ₹10–14 lakh fleet-sedan band we intend to compete in.

*Correction: an earlier draft claimed the eVX was "unlikely to contest the segment before
2028". Published launch estimates conflict widely — from late 2026 to early 2029 — so the
timing is not something we can assert. The **price band** is the defensible point: even at
its cheapest estimate, the eVX is ~30% above our band.*

**2034 addressable volume: 60,000–80,000 units/year** for a competitive sedan. *(All volume
forecasts are secondary/analyst — no official government forecast exists. Labelled as such.)*

---

## 4. Duty cycle — verified, not assumed

| Quantity | Value | Source |
|---|---|---|
| Base consumption | 12.84 kWh/100 km | Corrected from deck's 15.38 |
| Daily energy | **25.68 kWh/day** | Real-world verification |
| Annual equivalent full charges | **~200 EFC/yr** (190–228 range) | Corrected from deck's 365 |
| Deck's original figure | 38.28 kWh/day | **~49% overstated** vs verified |

The deck originally claimed HVAC alone was "2.24× overstated." That framing is wrong — the
overstatement is ~49% on total daily energy. Corrected.

---

## 5. The lifecycle model

### 5.1 Structure

```
SoH(t, EFC) = 1.02 − A_cal·t^α·Arrhenius(T)·k_SOC − k_cyc·DoD^β·Arrhenius(T)·(EFC·8)
```

| Term | Meaning | Primary source |
|---|---|---|
| `A_cal` | calendar capacity-fade coefficient | **Naumann 2018** (`10.1016/j.est.2018.01.019`) |
| `α` | calendar **time exponent** — **contested, 0.45–1.00** | Lewerenz 2017 vs Gasper 2021 |
| `β` | **DoD exponent** — **contested, −0.40 to +1.00** | Schreiber / Gauthier / Eldesoky |
| `Ea` | activation energy | Naumann: 17.126 kJ/mol (capacity), 71.827 kJ/mol (resistance) |
| `k_SOC` | SOC dependence | Naumann cubic, `0.6140` at 66% mean SOC (literal) |

### 5.2 Calibration provenance — Naumann 2018

Cell: Sony/Murata **US26650FTC1**, 3 Ah, 26650 cylindrical **LFP/graphite** — the same cell
family Graner used. 885 days, 17 test points × 3 cells, <2.2% max error on capacity fade.

**A normalisation detail worth stating**, because it was one of our own errors and it changes
the numbers: Naumann's Eq. (6) divides `k_SOC(SOC_ref)` **out** of `k_ref`, so the forward
model multiplies by `k_SOC(SOC) = 0.6140` at 66% mean SOC. An earlier draft used the
renormalised ratio `0.6399` instead — the two are **not** equivalent (4.06% on calendar fade,
**28.72% on resistance growth**).

### 5.3 Default results (Naumann literal, DoD^1.0, α = 0.50, linear superposition)

| Cell temp | Pack | EFC/yr | EFC @ yr 8 | SoH @ yr 8 | R_inc @ yr 8 |
|---|---|---|---|---|---|
| **48 °C** | **44.2 kWh** | 193 | 1548 | 71.6% | **+101.3%** |
| **40 °C** | **41.3 kWh** | 207 | 1657 | 76.7% | +50.9% |

### 5.4 Full parameter sweep — 48 °C cell

| DoD exp | α = 0.45 | α = 0.50 | α = 0.75 | α = 1.00 |
|---|---|---|---|---|
| **−0.40** | 50.0 kWh / 63.5% | 51.3 / 61.8% | 62.9 / 50.4% | **100.1 / 31.7%** |
| **0.00** | 47.1 / 67.3% | 48.3 / 65.7% | 58.0 / 54.7% | 87.6 / 36.2% |
| **+0.25** | 45.9 / 69.1% | **46.9 / 67.6%** | 55.9 / 56.7% | 83.2 / 38.1% |
| **+0.50** | 44.8 / 70.7% | 45.9 / 69.1% | 54.4 / 58.3% | 80.1 / 39.6% |
| **+1.00** | 43.3 / 73.2% | **44.2 / 71.6%** | 52.1 / 60.8% | 76.1 / 41.7% |

*Bold = model default.* Full 40 °C sweep also computed.

### 5.5 Thermal scenario envelopes

| Scenario | Cell | Pack range | SoH range | R_inc @ yr 8 |
|---|---|---|---|---|
| Immersion *(indicative)* | 26 °C | 37.1–53.3 kWh | 59.5–85.5% | +14.0% |
| **Proven chiller loop** | **40 °C** | **40.6–74.6 kWh** | **42.5–78.1%** | **+50.9%** |
| **Liquid plate** | **48 °C** | **43.3–100.1 kWh** | **31.7–73.2%** | **+101.3%** |
| Passive / air only | 55 °C | 46.2–**140+** *(no convergence)* | 22.0–68.6% | +179.8% |

### 5.6 The 55 °C result is a specification failure, not a sizing problem

At 55 °C cell the DoD exponent is **−0.40**, so *shallow* cycling becomes the **worst** case
— the exact opposite of 40 °C. Combined with the linear calendar exponent, the worst corner
exceeds the model's 140 kWh search ceiling.

**At 55 °C cell the duty is not achievable at any pack size the model can search.** We
deliberately did **not** raise the ceiling to manufacture a finite number. The
infeasibility is the finding. The deck's 45 kWh sedan is out by roughly **3×**.

### 5.7 An independent cross-check on the cell the model is calibrated to

Our entire calibration rests on one cell: the **Sony US26650FTC1** LFP/graphite cell in
Naumann 2018. That is a real exposure, so it is worth showing that cell has been independently
benchmarked by an unrelated group.

**Harlow et al. 2019** (*J. Electrochem. Soc.* 166(13) A3031–A3044,
`10.1149/2.0981913jes`) took Dalhousie's state-of-the-art NMC532/graphite pouch cell and
tested it for up to three years at **20, 40 and 55 °C**, both cycling and storage — and
plotted its own storage fade **directly against Naumann's LFP/graphite Sony US26650FTC1 cells**
in Fig. 3, the same cell our model uses.

Two things follow, and they point in opposite directions:

- **It validates the reference cell.** Our cell is the field's benchmark reference, not an
  obscure dataset. Harlow treats it as the comparison baseline precisely because it is
  well-characterised.
- **It does not transfer to us.** Harlow's 1.6 million km headline belongs to an NMC cell
  cycled to a **4.3 V** upper cutoff — a higher ceiling, a better-sealed pouch format, and
  a chemistry with a different degradation profile. It is an **upper bound for the best
  benchmark cell in the field**, not a number our LFP pack can claim.

Harlow also states plainly that *"the cycle and calendar lifetime of LFP/graphite cells are
superior to that of NMC/graphite cells"* — a same-field bridge from the reference cell to our
chemistry. **It still contains no LFP depth-of-discharge matrix**, so §6.2 remains open.

---

## 6. The two contested parameters

### 6.1 Calendar time exponent — 2.3× spread

| Source | Chemistry | Method | α |
|---|---|---|---|
| Liu 2018 | LFP | fitted power law | 0.4155 |
| Gasper 2021 | NMC + LFP pooled | statistical validation, 17 datasets | ~0.45 |
| Naumann 2018 | **LFP** | fitted √t | 0.50 |
| **Lewerenz 2017** | **LFP** | **measured linear fade, 50 cells** | **1.00** |

Gasper's finding is that a **fixed** t^0.5 is statistically invalid — only **1 of 17**
datasets contained 0.5 within its own 95% confidence interval, despite R² ≥ 0.99. But
Gasper also finds the exponent **rises toward 0.5 as temperature increases**, which pulls
against Lewerenz at our operating point. The literature does not converge.

### 6.2 DoD exponent — small, direction-ambiguous, and **not** a temperature function

| Source | Chemistry | Cell temp | UCV | β |
|---|---|---|---|---|
| Schreiber 2025 | NMC/graphite | 20 °C | — | 0.00 (flat) |
| Gauthier 2022 | NMC622/NG | 20 °C | 4.10 V | non-linear |
| Gauthier 2022 | NMC622/NG | **40 °C** | 4.10 V | **+1.00** |
| **Eldesoky 2022** | **NMC811/AG** | **20 & 40 °C** | **4.06 V** | **no dependence at all** |
| **Eldesoky 2022** | **NMC811/AG** | **20 & 40 °C** | **4.20 V** | **small, slightly INVERSE** |
| Eldesoky 2020 | **LFP** | 55 °C | 3.65 V | **−0.40** |
| *Our interpolation* | — | *48 °C* | — | *+0.25 — ASSUMPTION* |

**This kills the temperature hypothesis.** We had modelled the DoD exponent as crossing zero
with temperature. Eldesoky 2022 shows two NMC papers at **the same 40 °C** giving opposite
answers: Gauthier linear **+1.0**, Eldesoky small and **inverted**. The literature disagrees
even at fixed temperature. Our interpolated zero-crossing near 50.7 °C is an artefact of
stitching different chemistries at different voltages, not a physical law.

**Eldesoky 2022's headline result is that the DoD effect is simply SMALL:**

> *"Overall, the impact of DOD on capacity loss and ΔV growth was small… **differences between
> the various DODs in Fig. 4 were within 10–15 mAh which is small**."* — across the entire
> 25→100% DoD range, after **12,000 hours** of cycling.

### 6.2.1 The reconciling variable is upper cut-off voltage, not temperature

Eldesoky 2022 varied the **lower cut-off** to set DoD (25/50/75/100%) against two upper
cut-offs, and the UCV determined whether a DoD effect existed at all:

| UCV | DoD / C-rate dependence |
|---|---|
| **4.06 V** | **None.** *"the 4.06 V cells showed no C-rate- or DOD-dependency"* for impedance growth |
| **4.20 V** | Small and **inverse**: *"larger DODs generally resulted in smaller capacity loss"* |

The stated mechanism is identical to Eldesoky 2020's:

> *"a slight increase in capacity loss with **smaller** DODs which we attributed to the fact
> that the cells spent **more time at higher voltages** when the DODs were small"*

**So DoD is a weak lever; high-voltage dwell is the strong one.** Two independent studies,
different chemistries, different voltage windows, reach the same mechanism.

### 6.2.2 Why this is a strong argument *for* LFP

LFP's charge ceiling is ~3.6 V — **below Eldesoky's 4.06 V threshold at which DoD and C-rate
dependence vanish entirely.** We are not choosing to limit the DoD dependence; our chemistry
is already below the level where it appears.

It also validates the design requirements already in the document (`CW-1…CW-5`): a ceiling on
time-at-high-SoC, a charge window, and mandatory relaxation. Those are not housekeeping —
they are the levers that actually control degradation in this evidence.

**Post-mortem confirmation:** *"no separator discoloration or signs of Li plating on the
anode"* (2% VC + 1% DTD electrolyte). The cutoff-based DoD variation was **not** confounded
by plating — the confound we were worried about is ruled out.

### 6.3 What this means for the model

**β is secondary. The calendar exponent α dominates.** Holding α = 0.50 at 48 °C:

| β | Pack |
|---|---|
| −0.40 | 51.3 kWh |
| **0.00** | **48.3 kWh** |
| +1.00 | 44.2 kWh |

A 7 kWh spread across the *entire* β range. Holding β = +1.00 and varying α: **44.2 → 76.1
kWh**, a 32 kWh spread. Eldesoky 2022 independently supports β near 0.

**Revised position: β should be treated as a small parameter near zero, not a free variable
swept across ±1. The α dispute remains the dominant open question, and Eldesoky 2022 does
nothing to resolve it.**

### 6.4 What this means for the proposal

We cannot resolve either parameter from published LFP data at our operating point. We could
pick a value, but picking one and presenting it as fact would be the specific failure mode
this audit was commissioned to eliminate.

**The engineering response is the validation programme in §8, not a better guess.**

---

## 7. Two findings that changed the proposal

### 7.1 The literature disagreement, and why it is decisive

Two peer-reviewed studies. Same LFP chemistry. Same 40 °C. Opposite answers:

| Study | Method | Time dependence | Years to 80% SoH at 40 °C |
|---|---|---|---|
| Naumann 2018 | Fitted √t law | t^0.5 | **13.3 yr** |
| **Lewerenz 2017** | **Measured linear fade rate** | **t^1.0** | **3.7 yr** |

Lewerenz measured linear fade at 40 °C of **1.50–1.90% per 100 days** across 20–100% SOC,
with weak SOC dependence (~7% from 50% to 100% SOC) — which independently corroborates
Naumann's flat-mid-range finding. Their own extrapolation: **">3–4 years storing at 40 °C."**

**Our model reproduces 3.69 years from Lewerenz's own Table 6 slopes.** That is a
cross-check, not an assertion — and it reproduces the *conservative* paper, not the
favourable one.

**The paradox that makes this obvious in hindsight:** Lewerenz is **slower in year one**
(5.96%/yr vs Naumann's 9.8%/yr) and **far worse by year eight**. Long-horizon life is
governed entirely by the exponent, not the year-one rate.

> **Anyone who validates at year one and extrapolates linearly will get the 8-year answer
> backwards.** This is the single most important thing we learned.

**Consequence:** the previously derived "≤40 °C cell is a hard requirement" is **not
sufficient**. Under the Lewerenz exponent, an 8-year / 80% warranty is unreachable at 40 °C
on calendar ageing alone. Either the warranty target drops, the temperature envelope
tightens well below 40 °C, or the claim ships with the spread attached.

### 7.2 Resistance growth — an exposure nobody had modelled

Naumann's measured activation energy for **resistance** growth is **71.827 kJ/mol — 4.2× the
17.126 kJ/mol for capacity.**

| Cell temp | R_inc @ yr 8 | Implied peak power |
|---|---|---|
| 40 °C | +50.9% | ~66% of new |
| **48 °C** | **+101.3%** | **~50% of new** |

At 48 °C the pack reaches **80% SoH on paper while delivering roughly half its rated power.**
Naumann's resistance term is **linear in time**, not √t — so it does not share the calendar
exponent controversy, and this exposure is present under *every* parameter combination in
the sweep.

**A capacity warranty covers none of this.** An 8-year fleet vehicle delivering half its
rated power is a warranty event that state-of-health cannot see. **This requires its own
warranty clause** — a power-delivery threshold, not a capacity threshold.

---

## 8. Validation programme

**Six cells · 40–45 °C · 90–100% SoC · ≥18 months · replicated.**

### 8.1 Why these exact parameters

| Parameter | Value | Justification |
|---|---|---|
| Cells | 6 (from 3) | Spread uncertainty scales as 1/√(2(n−1)): **~50% at n=3 → ~32% at n=6** |
| Temperature | 40–45 °C | Our realistic operating point, and the band where literature disagrees most |
| SoC | 90–100% | Where calendar fade is strongest; Graner's lab matrix had no points above 87.5% at 40 °C |
| Duration | ≥18 months | Must span at least one seasonal cycle |

### 8.2 The quantitative justification

Graner et al. (arXiv 2609.10185) built a probabilistic LFP degradation framework on 17
calendar + 19 cyclic conditions, 3 replicates each, 885 days, validated against 21
residential systems over 5.2 years.

**Their full predicted end-of-life range was ~3 years on a 12.3-year mean — about 33% of
lifetime.** And critically:

> **One outlier cell at a single frequently-visited condition (25 °C / 100% SoC, 5.9% spread)
> accounted for ~50% of the entire EOL range.** Replacing it narrowed the range from 3 years
> to 1.5 — a **50% reduction**.

**This is the argument judges cannot dismiss:** our gap is not rhetorical. In a
better-instrumented dataset than ours, a single anomalous cell moved the answer by half.
Without replication we cannot even *detect* such a cell.

### 8.3 What this one programme closes

| Gap | Closed by |
|---|---|
| Calendar exponent (0.45 vs 1.0) | High-SoC holds at our temperature, past 18 months |
| Activation energy | 40–45 °C cell data at our SoC |
| SOC dependence | 90–100% SoC arms |
| Replicate-derived outlier risk | n = 6 vs n = 3 |

**This converts our largest weakness into a costed, dated, defensible plan.** That is the
single strongest element in the proposal.

---

## 9. What we will not claim

| Claim | Status | Reason |
|---|---|---|
| "8-year / 80% SoH" | **Not defensible at 40 °C** | Lewerenz vs Naumann disagreement unresolved |
| Xpres-T fleet share 89%→53% | **Removed** | No primary corroboration exists |
| Fleet orders −92% | **Removed** | Cited article does not exist |
| A single pack size | **Removed** | Range is the honest answer |
| Market-share argument | **Replaced** | TCO parity + gazetted mandates, both primary |
| Na-ion as primary chemistry | **Replaced with LFP** | Three independent certification walls |
| Charge rate as a design constraint | **Removed** | Not a real constraint at our duty |
| "HVAC 2.24× overstated" | **Corrected** | ~49% on total daily energy, not HVAC alone |

---

## 10. Appendices

### Appendix A — Evidence base (all DOIs verified against Crossref)

| Source | Citation | Role |
|---|---|---|
| Naumann et al. 2018 | *J. Energy Storage* 17, 153–169 · `10.1016/j.est.2018.01.019` | LFP calendar model: Ea, SOC factor |
| Lewerenz et al. 2017 | *J. Power Sources* · 50-cell LFP dataset | Linear fade measurement at 25/40/60 °C |
| Simolka et al. 2020 | *J. Appl. Electrochemistry* 50, 1101–1117 · `10.1007/s10800-020-01465-6` | LFP DoD + temperature post-mortem |
| Schreiber et al. 2025 | *J. Energy Storage* 112, 115357 · `10.1016/j.est.2025.115357` | Realistic VW ID.3 duty cycling |
| Gauthier et al. 2022 | *J. Electrochem. Soc.* 169, 020518 · `10.1149/1945-7111/ac4b82` | DoD × C-rate × calendar matrix |
| Gasper et al. 2021 | *J. Electrochem. Soc.* 168, 020502 · `10.1149/1945-7111/abdde1` | t^0.5 statistical invalidity |
| Eldesoky et al. 2022 | *J. Electrochem. Soc.* 169, 100531 · `10.1149/1945-7111/ac99a6` | DoD × C-rate × voltage × temperature |
| Graner et al. 2026 | arXiv `2609.10185` | Lab-to-field uncertainty, probability bands |
| Waldmann et al. 2014 | *J. Power Sources* 262, 129–135 | 25 °C temperature mechanism crossover |
| Pozzato et al. 2023 | *Joule* · `10.1016/j.joule.2023.07.018` | Real-world field behaviour |
| **Harlow et al. 2019** | *J. Electrochem. Soc.* 166(13) A3031–A3044 · `10.1149/2.0981913jes` | 3-yr NMC532 benchmark; plots itself against Naumann's LFP reference cell |

**Outstanding gap:** Louli & Dahn / Harlow et al. 2019 LFP DoD matrix
(`10.1149/2.0981913jes`) — the supplied file is Harlow et al. 2019, **NMC532**, not LFP.

### Appendix B — Corrections made to the original proposal

| # | Original | Correction |
|---|---|---|
| 1 | 38.28 kWh/day consumption | **25.68 kWh/day** real-world (−33%) |
| 2 | "HVAC 2.24× overstated" | ~49% on **total** daily energy |
| 3 | 365 EFC/year | **190–228 EFC/year** |
| 4 | 45 °C ageing claim | Restated on published Arrhenius basis |
| 5 | Charge-rate constraint row | **Removed** |
| 6 | Reliance / Faradion milestone | **Replaced** |
| 7 | Single 40 kWh pack size | **Range** across measured parameter space |
| 8 | 8-year / 80% SoH warranty | **Qualified** — not defensible at 40 °C without validation |
| 9 | Xpres-T fleet share 89%→53% | **Removed** — no primary corroboration |
| 10 | Fleet orders −92% | **Removed** — source article does not exist |
| 11 | Na-ion as primary chemistry | **LFP primary**, sodium as documented 2036–38 option |
| 12 | — | **Resistance-growth warranty clause added** (never previously modelled) |

### Appendix C — Model provenance and error log

All figures reproduce from `/tmp/opencode/mach1/mach1_model.py`, independently verified by
`/tmp/opencode/mach1/self_audit.py` (**exit 0**).

- Default calibration: **Naumann 2018, literal SOC convention** (verified against Eq. 3 + 6)
- Calendar exponent sweep: **0.45 / 0.50 / 0.75 / 1.00**
- DoD exponent sweep: **−0.40 / 0.00 / +0.25 / +0.50 / +1.00**
- Hard model floor: **25 °C cell** (Waldmann mechanism crossover; `solve_min_pack` raises below)
- Structural uncertainty band: **40–50% on the 8-year EOL claim** — Graner-derived lower bound
  for data this sparse, reported separately and never merged into the parameter sweeps

**Two errors of ours are preserved in the model's correction log rather than silently
overwritten**, so the chain stays auditable:

1. **Naumann SOC normalisation** — we used the ratio (0.6399) instead of the paper's literal
   value (0.6140). Error size: **4.06% on calendar fade, 28.72% on resistance growth.** The
   discarded form also manufactured a false finding (66% SoC appearing 2.07× worse than
   100% for resistance). The audit carries a standing correction so it cannot be re-quoted.

2. **Two wrong DOIs.** Gasper 2021 and Naumann 2018 citations carried incorrect DOIs in
   earlier drafts. In both cases the **article numbers were correct** and only the DOIs were
   faulty. Naumann's erroneous DOI resolved to an unrelated pumped-storage paper. Both now
   verified; the dead DOIs remain in the log for traceability.

**Method note.** Where a specialist agent's conclusion was checked and found incorrect, the
correction was made against the primary source and the disagreement recorded rather than
quietly overwritten — twice in this project, and both corrections are in the artifacts.