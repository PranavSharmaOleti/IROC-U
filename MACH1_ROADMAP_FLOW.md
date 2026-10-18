# FleetLine E1 — Road to 2035

```
 PHASE 1  2026–27          GATE              PHASE 2  2028–30       GATE        PHASE 3  2031–35
 Delhi NCR                 G1 CELL           Delhi                   G4 SCALE    Pan-India
 1,000–2,000 veh           G2 DUTY           Bengaluru               G5 CELLS    100,000+ cum.
 margin segment            G3 BATTERY        Mumbai
   │                         │                  │                         │            │
   └── 5 gates, all measurements ─ not dates ─────────────────────────────┘            │
```

Gates are **measurements, not calendar milestones.** Each has a threshold and a failure action.

| Gate | Measure | Threshold | If it fails |
|---|---|---|---|
| **G1 CELL** | Qualified LFP sources | Two, price parity within 10% | Stay dual-imported; do not commit Phase 2 volume |
| **G2 DUTY** | Measured paid km/day | ≥ 200 | Re-run the TCO before scaling — the case is duty-sensitive |
| **G3 BATTERY** | Per-cell SoH telemetry | 12 months, closing the **3.6×** disagreement in published LFP time-to-80% | Capacity-retention guarantee is unsignable |
| **G4 SCALE** | Cumulative fleet | 20,000 vehicles, 21.9 h/month downtime slack held against a 25–40% public-charger session-failure rate | Hold at Phase 2 footprint |
| **G5 CELLS** | Domestic LFP capacity | **>20 GWh operating, automotive-qualified** | Localisation claim stays at pack assembly |

---

## Phase 1 · 2026–27 · Delhi NCR

- **1,000–2,000 vehicles** — indicative and gate-conditional, not a forecast
- **Segment:** airport transfers + corporate commute. Launch here because EV adoption is 18% against 10% street-hail, and dispatch is pre-booked
- **Charging:** 1 × 7.4 kW AC port per vehicle, 10% N+1 spares, **₹99,000/vehicle installed**
  Overnight window 25.68 kWh ÷ (7.4 kW × 0.90) = **3.86 h**. One port is enough. No DC fast-charging required
- **Cells:** Reliance Jamnagar LFP primary, qualified import as bridge, dual-sourced from day one
- **Power:** ₹4.50/kWh Delhi BEE EV tariff

## Phase 2 · 2028–30 · Delhi + Bengaluru + Mumbai

All three cities clear at five years on the published basis. Cumulative 15,000–25,000 vehicles.

## Phase 3 · 2031–35 · Pan-India

100,000+ cumulative. Deep localisation proceeds **only** if G5 is met.

---

## Localisation

| | Window | Content |
|---|---|---|
| **L1** | 2026–27 | Pack assembly, BMS, thermal management, vehicle integration |
| **L2** | 2028–30 | Domestic LFP cells for a share of volume; imported for the balance |
| **L3** | 2031+ **if gated** | Domestic cells plus CAM, AAM, separator content |

**The honest ceiling.** ACC PLI has delivered **1.4 GWh of 50 GWh — 2.8%** — and all of it from one company. Domestic value addition sits below the 60% DVA threshold because CAM, AAM, separators, electrolytes and foils are imported. Reliance Jamnagar is the LFP player (40 GWh, ramping through H2 2026). Ola Cell is the only Indian producer at scale and is NMC-first — the wrong chemistry for this vehicle, which is why dual-sourcing is the plan and not the exception.

## Infrastructure

- **One AC port per vehicle.** CCS2 mandated for four-wheelers by the **2022 amendment to AIS-138 Part 2**; OCPP 1.6J
- **Range envelope: 268 km at 15% reserve** (315 km at zero reserve)
  - Feasible one-way: Delhi–Agra 200 · Mumbai–Pune 150 · Mumbai–Nashik 170 · Bengaluru–Mysuru 145
  - Marginal: Delhi–Jaipur 280 — 88.8% of usable pack
  - **Beyond ~300 km, destination charging is mandatory — a fleet-contract requirement, not a vehicle spec**
- **25–40% public-charger session-failure rate** (300,000+ model/OEM/CPO combinations) against **21.9 h/month** of real downtime slack. This is the operational risk that binds, not range

## Policy

| State | What it gives | Expiry |
|---|---|---|
| **Delhi** | 0% road tax for the life of the vehicle; ₹1 lakh scrapping incentive. **No purchase incentive for electric cars** | **31-Mar-2030** |
| **Maharashtra** | **15% of ex-factory, capped ₹2 lakh, transport e-4W — 25,000 units**; 100% toll exemption on the Mumbai–Pune Expressway and Samruddhi Mahamarg; EV road-tax exempt | **31-Mar-2030** |
| **Karnataka** | 20–25% capex subsidy, stamp-duty reimbursement, three plug-and-play clusters. No consumer incentive | 2030 |
| **Central** | **PM E-DRIVE has no e-4W category at all** — ₹11,900 cr covers 2W, 3W, rickshaws, ambulances, trucks, buses | 31-Mar-2028 |

**Delhi and Maharashtra both expire five years before the 2035 target.** Renewing them is a policy position, not an engineering one, and it is worth roughly 5 points on the five-year case.

## Economics

NPV at a 12% hurdle, escalated, financed 60 months, **including the ₹99,000 charger**.

| | Delhi | Mumbai | Bengaluru |
|---|---|---|---|
| **5-year** | **+6.7%** | **+4.0%** | **+0.9%** |
| **8-year** | **+14.6%** | **+10.6%** | **+9.0%** |
| 2035, 5-year | +15.7% | +10.4% | +9.0% |
| 2035, 8-year | +23.1% | +16.4% | +16.3% |

**One negative cell in the whole 48-cell model:** Bengaluru, 5 years, cash purchase, −0.4%.

**Where it breaks.** Power-escalation break-even at five years is **Delhi 14.5%/yr, Mumbai 8.8%, Bengaluru 8.7%**. Electricity escalation is unambiguously bad for the EV in every city — worst in Mumbai at −9.2 points — and the CNG leg is what carries the case. Do not present escalation as good news.

---

*Every figure regenerates from `MACH1_WORKING_FILES/tco_engine/` (sections A–R). Detailed sourcing in `MACH1_IMPLEMENTATION_ROADMAP_DETAILED_SUPERSEDED.md` and `MACH1_TCO_ANALYSIS.md`.*