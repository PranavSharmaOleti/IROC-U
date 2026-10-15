# ITEM 1: Is either chemistry feasible?

*Verbatim from opencode session, 2026-10-15. Preserved at user request.*

## Sodium-ion: no. Three independent walls, all of which have to fall.

**Wall 1 — the cell doesn't exist at your scale.** No supplier on Earth has layered-oxide sodium-ion in a sedan-class vehicle. The only automotive deployments are A00 microcars with 23–25 kWh packs (HiNa in the JAC Yiwei 3, Farasis in the JMEV EV3). The one Na-ion with GWh capacity *and* a passenger car *and* GB 38031-2025 certification is CATL Naxtra — and that's **Prussian White**, a different cathode family from the layered oxide your proposal specifies.

**Wall 2 — the data doesn't exist.** Zero cycle-life data for any layered-oxide cell at 60–80% DoD *and* 40–45 °C. Every headline claim has undisclosed DoD and/or temperature. RWTH tested commercial layered-oxide cells to 45 °C but only for *calendar* ageing; TUM found severe 45 °C degradation at high SOC, and again no cycling. LFP by comparison has WRI data: 2,000 cycles at 45 °C. You can't build a comparison when one side has no number.

**Wall 3 — you cannot legally homologate it in India.** AIS-038 Rev.2 Amendment 3, Annex IX-K(2), verbatim:

> *"Cells used to make REESS, shall be certified as per IS 16893-Part 2 and Part 3 by NABL accredited lab or by test agency notified under CMV Rule 126."*

IS 16893-2/-3 are titled *"Secondary **Lithium-Ion** Cells…"*. No amendment through Amd 4 has added a scope exemption or alternative-chemistry clause. No sodium-ion cell has ever been certified to them. **There is no legal import route either** — importing a finished pack doesn't help, because the pack must itself be type-approved under AIS-038, which requires the cell certification.

Joint probability of all three clearing by January 2034: **under 10%.**

## The sodium-ion cost/regulatory detail that cuts *against* the deck

| | |
|---|---|
| HSN | 8507.60 is **"Lithium-ion accumulators"** only. Na-ion falls under 8507.80 "Other accumulators" → **15% BCD**, not 20% |
| 5% concessional BCD | Operative text says **"Lithium-Ion Cells for batteries of EVs or BESS"** — excludes Na-ion |
| 0% capital-goods BCD | Says **"for Lithium Ion Cell manufacturing"** — excludes Na-ion |
| GST | **Uniform 18%** across heading 8507 post-GST-2.0; PIB explicitly names sodium in the 28%→18% cut |

So Na-ion gets a *slightly* lower headline duty (15% vs 20%) but loses every concession, and GST is neutral. Net: no duty advantage either way.

## LFP: yes, with a supply chain problem you should be honest about

Exide is the only near-term supplier with an operating automotive LFP plant (6 GWh, Sep 2026, SVOLT licence, Hyundai/Kia PV partnership). Agratas is the 2027–29 volume play. **Every 45 kWh pack sold in India today uses imported Chinese cells** — EVE, Gotion, or BYD Blade. Reliance has zero cells installed and paused. JSW is on hold with no tech partner.

Pricing: ₹5,200–6,000/kWh today → **₹3,700–3,900/kWh by 2034**, i.e. ₹1.67–1.76 lakh for 45 kWh. Your deck's ₹8,500/kWh floor is ~40% too high, which means **₹14 lakh is more achievable than your own arithmetic implied.**

Two thermal findings that matter more than the supplier list:
- **LFP cycle life halves at 45 °C** (WRI: 4,000 cycles @25 °C → 2,000 @45 °C). At your 228–277 EFC/yr that's **7.2–8.8 years** — tight against an 8-year requirement, not comfortable.
- **EMO Energy's fleet data: 85% SoH at 75,000 km with immersion cooling holding cells at 24–28 °C.** Their own conclusion: *"active thermal management critical."*

The engineering answer to your duty cycle is **money in the cooling loop, not a bigger pack.**

---

## Now — the novelty, because that's what you actually asked

Here's the thing I'd push back on, gently. The novelty isn't gone. It moved.

**BIS has four sodium-ion standards in active development** — ETD 11 items 33354 (performance testing), 33355 (safety requirements), 33358 and 33359 (industrial applications), mirroring IEC PNW 21-1241/1242. They are drafts, unpublished.

**NITI Aayog's July 2024 report said so explicitly:**

> *"India's existing application standards … (like AIS-038, AIS-156, etc.) **inherently impede certification** of emerging energy storage technologies."*

It asked BIS to notify chemistry-agnostic standards and amend AIS-038/156 **within 3–4 months**. That was over two years ago. **Nothing has been done.**

That is a real, citable, verifiable problem — and it is the actual reason sodium-ion can't happen in 2034, more than cell supply is. Nobody else in your field is looking at it.

So the honest version of the proposal is not *"we'll use sodium-ion."* It's:

> **The first Indian fleet-EV programme designed against its actual duty cycle, with chemistry-agnostic pack architecture and a dated homologation gate.**

Which includes: LFP as the 2034 build, a modular non-structural pack that keeps a chemistry swap cheap, thermal management sized for45 °C rather than for a badge, and a documented regulatory watch with BIS ETD 11 as the trigger for a 2036–38 sodium-ion variant.

That's more novelty than the chemistry version, because it's novelty nobody can copy without doing the work — and every claim in it survives a hostile question.

---

## Supporting supplier data (for the record)

### Sodium-ion — global manufacturing reality (Oct 2026)
- **CATL Naxtra** — Prussian White, 175 Wh/kg, 10 GWh (2025) / 30 GWh (2026) / 100 GWh (2030 target). GWh lines operational Fuding. 60 GWh HyperStrong order (Apr 2026). **GB 38031-2025 certified 5 Sep 2025 (world's first Na-ion).** Changan Nevo A06 deliveries mid-2026. Cycle claim: 10,000 with **no DoD/temperature disclosed**.
- **HiNa** — layered oxide, cylindrical 32140, 165 Wh/kg, 1 GWh (2022) / 5 GWh (2023). JAC Yiwei 3 since Jan 2024 (A00, 23.2 kWh). 4,500 cycles claimed, conditions undisclosed.
- **BYD** — layered oxide, 30 GWh Xuzhou line, Qinghai line operational Jul 2025. **No production EV confirmed.**
- **Farasis** — layered oxide pouch, 3.8 GWh. JMEV EV3 (A00, Dec 2023).
- **Natron Energy (US)** — **ceased operations 3 Sep 2025.**
- **Faradion (Reliance)** — effectively zero capacity, "on hold."
- Best published high-temp cycling for layered oxide: **200 cycles, 95% retention, 45 °C, 1C** — academic, not commercial.
- Cost parity: WoodMac ~2035; BCG 2030–2035 (leading) / post-2030 (broad); Nature Energy (Yao 2025) 40% of 6,048 modelled scenarios reach parity by 2030.
- Scenario spread: Best 15–20% (2032–34 feasible) / Base 50–60% (2036–38 earliest) / Worst 25–30% (never).

### Sodium-ion — India route
- No legal route today. No foreign Na-ion cell holds BIS ISI or AIS-038/156 approval.
- **BIS ETD 11 drafts in progress:** 33354 (perf testing), 33355 (safety requirements), 33358 + 33359 (industrial applications). Mirrors IEC PNW 21-1241/1242.
- **Rechargion Energy** (CSIR-NCL spin-off, Pune) validated Na-ion cells against IS 16893/IEC 62660 methods at ARAI, Aug 2025 — testing against the *lithium-ion* standard, not a Na-ion standard. Closest thing to a legal route.
- **NITI Aayog Jul 2024** recommended chemistry-agnostic standards + AIS amendment in 3–4 months. **>12 months overdue.**
- PLI-ACC allocated **zero GWh to sodium-ion** across two rounds.
- Domestic ecosystem: Reliance/Faradion (paused, PLI Milestone-1 missed, ₹31M liquidated damages); HiNa+Cygni (3W/telecom only); KPIT+Trentar (3 GWh, no groundbreaking); JNCASR (lab, TRL 4–5); Naxion (1.5 GWh pack assembly, cell plant unfunded); GODI (pivoting to supercapacitors).
- Path to Jan 2034: BIS standard Dec 2027 → MoRTH amendment Jun 2028 → lab accreditation Dec 2028 → domestic ≥1 GWh Dec 2029 → homologation Jun 2031 → SOP Jan 2034. **<10% joint probability.**
- Precedent: LFP took 3–4 years from first cell availability to volume M/N homologation. Na-ion starts further behind (IEC standards still NP/WD).

### LFP — India supply (Oct 2026)
| Company | Announced | Operating | Notes |
|---|---|---|---|
| Ola | 5→20→100 GWh | **1.4 GWh** | Scooter cell; BIS certified |
| Exide | 6→12 GWh | **6 GWh (Sep 2026)** | SVOLT licence; Hyundai/Kia PV |
| Agratas | 20→40 GWh | 0, **early 2027 target** | Tata captive |
| Amara Raja | 16 GWh | 0, **FY2027** | Gotion tie-up collapsed |
| Reliance | 40 GWh | **0, paused** | No cell equipment installed |
| JSW | 50 GWh | **0, on hold** | No tech partner — China curbs |

- Total domestic cell output 2026: **~2–4 GWh**.
- Every 45 kWh pack in India uses imported cells (EVE / Gotion / BYD Blade).
- **Maruti-specific:** TDSG cell production (Aug 2025) is **hybrids only (LTO/NMC), not BEV LFP.** e-Vitara runs a fully imported BYD Blade pack. Maruti is currently the most import-dependent major OEM for BEV batteries.
- Pricing: 2026 ₹5,200–6,000/kWh → 2034 ₹3,700–3,900/kWh. BNEF learning rate 18% (2025) supports 3.5%/yr real decline.
- Concessional 5% BCD expires 31-Mar-2028 → +₹36–45k per 45 kWh pack.
- **WRI India:** LFP 4,000 cycles @25 °C → **2,000 @45 °C** (50% loss).
- **EMO Energy fleet:** 85% SoH @75,000 km with immersion cooling (cells 24–28 °C), zero thermal runaway @45 °C ambient.
- **No published large-scale Indian passenger-car LFP degradation dataset exists.**