# MACH1 / FleetLine E1 — Market Assessment Rebuild

**India | Evidence review and decision note | 18 October 2026**

## Executive finding

The previous market assessment is withdrawn. It asserted unsupported trip purpose shares, 2035 rides, use-case growth, fares, EV penetration, price sensitivity, daily kilometres, and vehicle fit. It also treated five hand-assembled use cases as a clustering sample and ran regressions with five rows. Those outputs are not decision-grade and should not appear in the deck.

What the evidence currently supports is more limited:

1. A 2025 press report citing Motilal Oswal gives average daily rides of Uber **840,000**, Ola **460,000**, and Rapido **320,000**. Their sum implies **591.3 million platform rides per year** if the daily rate held for 365 days. This is a *platform-reported ride-flow proxy*, not a complete count of Indian taxi journeys; the article does not provide the underlying study's definitions or a clear vehicle-class breakdown. [Business Standard, 18 April 2025](https://www.business-standard.com/companies/start-ups/blusmart-s-shock-exit-leaves-india-s-green-mobility-market-up-for-grabs-125041800827_1.html)
2. A ₹300 average fare appears in an industry comment reported by *The Times of India*, alongside about eight trips per driver-day. It is a broad cab-economics reference, not the measured average fare of the airport, corporate, or E1 target segment. [Times of India, 23 June 2025](https://timesofindia.indiatimes.com/business/india-business/as-commissions-fall-indias-ride-hailing-firms-test-viability-of-flat-fee-economics/articleshow/122029891.cms)
3. Combining the ride-flow proxy with a clearly labelled target-share and fare sensitivity gives a **scenario range**, not a verified market estimate. At 5–15% target share and ₹300–₹600 per trip, the illustrative annual gross booking value is **₹887–₹5,322 crore**. The central arithmetic case (10%, ₹450) is **₹2,661 crore**. These are useful thesis-slide placeholders only until the target share and fare are measured.
4. VAHAN registrations and AutoPunditz sales data can measure the *vehicle supply, mix, and OEM competition* that MACH1 would sell into. They do not reveal trip demand, fare, paid kilometres, or airport/corporate booking share.
5. The correct next decision is a segment-level operating-data build, followed by a bottom-up city and use-case estimate. Do not claim that airport/premium is proven to be the highest-margin segment until operator economics support that statement.

## 1. Corrected market-size build

### Formula

For an annual rider-spend / GMV estimate:

```text
Annual addressable GMV
= observed annual ride count
  × target-segment share of those rides
  × average realized fare in the target segment
```

If the slide is intended to show MACH1's *vehicle sales opportunity*, this GMV is not the answer. Convert demand to vehicles with rides per active vehicle per year, then to new vehicle purchases using fleet growth/replacement and MACH1's attainable share:

```text
Target active vehicles = target-segment annual rides ÷ rides per active vehicle per year
Annual vehicle opportunity = target active fleet × (net fleet growth + annual replacement rate)
MACH1 units = annual vehicle opportunity × serviceable city share × attainable OEM share
```

The second conversion cannot yet be calculated: the evidence folder has no measured target-segment rides per vehicle, active taxi fleet stock, replacement cycle, or MACH1 conversion target.

### Inputs and calculation

| Input | Value used | Evidence status |
|---|---:|---|
| Uber average daily rides | 840,000 | Motilal Oswal figure cited by Business Standard (2025); scope/definition not exposed in the article |
| Ola average daily rides | 460,000 | Same source |
| Rapido average daily rides | 320,000 | Same source; report does not establish car-only scope |
| Combined daily rides | 1,620,000 | Sum of the three reported figures |
| Annualized rides | **591.3 million** | 1.62m × 365; run-rate annualization, not a separately observed annual total |
| Average fare | ₹300–₹600 | ₹300 is a broad all-cab reference; ₹600 is a sensitivity bound, not a measured target fare |
| Target share | 5–15% | Scenario range only; no validated India-wide segment share is available |

| Scenario | Annual rides × target share | Fare | Illustrative annual GMV |
|---|---:|---:|---:|
| Low | 591.3m × 5% = 29.6m | ₹300 | **₹887 crore** |
| Central arithmetic case | 591.3m × 10% = 59.1m | ₹450 | **₹2,661 crore** |
| High | 591.3m × 15% = 88.7m | ₹600 | **₹5,322 crore** |

**Reading the range:** the low and high cases deliberately combine multiple assumptions, so this is a sensitivity envelope, not a confidence interval. The target-share assumption dominates the answer. Airport, corporate, premium, and commute are overlapping classifications: a corporate airport booking can be both airport and corporate, and a premium ride may also be airport or intra-city. Never add those categories without de-duplicating trip records.

### What can go on the thesis slide today

> **India platform ride-flow proxy: ~591M trips/year (annualized from three reported platform daily counts).** If MACH1's serviceable segment represents 5–15% of those rides at ₹300–₹600 per ride, its illustrative gross booking pool is **₹0.09–₹0.53 lakh crore/year**. The range is scenario-led; segment share and realized fare still need operator or trip-level validation.

Use the central ₹2,661 crore arithmetic case only as a clearly marked illustrative midpoint. Do not call it TAM, SAM, or MACH1 revenue. Do not extend it to 2035 with a CAGR until the base series and segment allocation are validated.

## 2. What the old clustering and regressions establish

### Hierarchical clustering: remove from the findings

The earlier analysis had five manually constructed use-case rows and seven columns. It did not have rider, city, trip, or vehicle observations. The row labels were the analyst's own categories, and several inputs (including price sensitivity, daily duty, segment EV share, and segment growth) were unsupported or not measured on a common basis. Z-scoring seven features across five rows cannot turn those judgments into sampled market behavior. A distance matrix and linkage rule would make the arithmetic visible, but would not repair the sample or the provenance.

Therefore:

- Do not report the dendrogram, merge heights, cluster labels, or “independent agreement.”
- Do not replace the method with K-means, DBSCAN, or another clusterer on the same five rows.
- First collect a city × service/use-case panel with multiple observed demand and operating metrics, and keep distinct trip-purpose, customer, service, and powertrain dimensions separate. Then use clustering only as exploratory segmentation, with standardized features, distance/linkage sensitivity, and stability assessed by resampling actual city-period cells.
- If the strategic decision is simply vehicle suitability, a transparent requirements matrix with evidence-backed constraints is more appropriate than clustering.

### Multivariate regression: no valid model in the current evidence

The prior five-observation regression had only two residual degrees of freedom after three predictors including the intercept. Its coefficients, standard errors, adjusted R², and residual ranking are not decision-grade. The second EV-share regression had the same five-row problem and used segment EV shares that were not measured. Remove both. A deterministic sensitivity table is not a substitute for empirical regression and must not be described as one.

A regression becomes useful when the unit of observation matches the question. For example, to test whether city and policy conditions predict four-wheel EV adoption, collect a **city/state × month** panel with EV and ICE registrations, policy dates, vehicle-type controls, charger availability, fuel prices, incentives, and market size. Use a pre-specified fixed-effects or difference-in-differences design only if there are enough treated/control jurisdictions and a credible pre-trend. That answers adoption in registrations; it still does not estimate taxi trips or rider preferences.

To estimate E1's target market, the preferred dataset is anonymized **trip-level or operator-month data**: origin/destination zone, purpose/booking channel, fare paid, trip and deadhead km, paid km, trip count, vehicle/fuel, downtime, city, and month. A panel model with city and month effects can then estimate volume/fare/utilization relationships. For rider value tradeoffs, use a properly sampled MaxDiff or choice-based conjoint survey; sales registrations cannot identify preferences.

## 3. Data reviewed in MACH1 working files

### VAHAN panel

`MACH1_WORKING_FILES/data/vahan_panel.csv` contains 16,274 records, four geographic units (Andaman & Nicobar Island, Andhra Pradesh, Arunachal Pradesh, Assam), 102 distinct period labels, 60 vehicle-class labels, and 37 fuel labels. The records span 2019 to October 2026, but the `month` field mixes bare year labels (such as `2019`) with month labels (such as `2019-JAN`); October 2026 may also be an incomplete current period. It is useful for exploratory registration mixes only after period parsing and aggregation rules are fixed. It is **not an all-India complete panel**: state coverage is four units, some class/fuel values are blank, and annual and monthly totals must not be added together. The extract does not carry collection timestamp, extraction specification, or clear completeness metadata. Reconcile those before quoting any total or trend.

The four-state, state-month registration series could support *descriptive* fuel-mix and OEM analyses after cleaning. With four states it is too narrow for a national claim and fragile for policy causal inference. Do not use it to estimate taxi fleet size unless commercial vehicle classes/permit status and active fleet stock are explicitly identified.

### AutoPunditz EV files

The local EV datasets are structurally model/month sales or registrations (for example, `autopunditz_ev.csv` has 188 rows from Feb 2020–Sep 2026; `autopunditz_ev_vahan_oem.csv` has 87 rows from Apr–Sep 2026). The file names and fields mix retail registrations, wholesale dispatches, market totals, and model rows. These series must be separated by source/measure before combining. They are a promising EV adoption and model competition panel, not taxi use-case data.

### AutoPunditz OEM wholesale data

AutoPunditz's car-sales archive publishes monthly OEM/model-wise sales pages and historical sales analysis. Its tables are valuable for *vehicle market* work: model share, segment mix, seasonal dispatches, launches, powertrain shifts, and competitive positioning. Treat wholesales (OEM dispatches) separately from retail VAHAN registrations; stock changes can make them diverge. AutoPunditz itself publishes both kinds of series, so each row needs a `measure_type` field before use. [Car Sales Figures](https://www.autopunditz.com/car-sales-figures) · [Electric Vehicle Sales](https://www.autopunditz.com/electric-vehicle-sales) · [Sales Analysis archive](https://www.autopunditz.com/sales-analysis). AutoPunditz describes its sales archive as covering the past decade; monthly pages provide model and OEM comparisons.

Recommended AutoPunditz extraction: one row per month × OEM × model × measure type, with source URL, publication date, period, units, domestic/export scope, and notes. Preserve the raw table; normalize OEM/model aliases in a separate mapping table. Do not infer taxi suitability from model sales alone.

### Autiqa Lens Pro screenshots and account

The screenshots in the working folder show Lens panels for passenger-vehicle overview, OEM landscape, state map, EV/green mobility, and a Delhi forecast. Controls include geography, year basis, year, OEM, fuel, and month. That can support a much richer **registration-led vehicle-market** workstream than the partial four-state CSV: state/OEM/fuel mix, market shares, trend and seasonality, model/OEM comparisons, and forecast backtesting.

The forecast screenshot shows Delhi, a 24-month Holt–Winters forecast, a projected value of 9.7 lakh, next-12-month value 4.5 lakh, and RMSE 23.5 thousand. Treat this as a dashboard-generated planning view, not a validated demand forecast: the metric is total actual registrations, the selected series and training period need to be recorded, and a backtest against simple baselines is not shown in the screenshot. It is not a ride-hailing or taxi forecast.

Autiqa's public data-status page says Lens Pro covers VAHAN history from 2012 to September 2026, with state/OEM/fuel/calendar-year/fiscal-year filters and detailed tables; it reports a 2,20,465-row bundled snapshot across 37 regions and 28 OEMs, generated from public registrations. It also cautions against summing state registrations to construct All India; use its published national series for national totals. [Autiqa Lens data status](https://autiqa.in/lens/data-status)

**Account access note:** Firefox was not exposed as an available browser surface in this session, so I did not query or export private Lens Pro tables. The screenshots were reviewed. For a next pass, export the same filters as CSV and include data dictionary, exact row/measure definition, latest refresh date, and coverage. No credentials are needed in chat.

## 4. The other linked data sources

| Source | Good use | Limits for this market assessment |
|---|---|---|
| [VAHAN dashboard](https://vahan.parivahan.gov.in/vahan4dashboard/) | Official vehicle registrations by category, fuel, maker, geography, and period; useful for new-vehicle supply/adoption | Registrations are not active fleet, trips, demand, price, or taxi-purpose labels; coverage/completeness and lag must be checked |
| [RevTpark Vahan scraper](https://github.com/RevTpark/vahan-scraper) | Reproducible batch extraction of VAHAN dashboard dimensions to CSV/XLSX; supports state, RTO, year, maker/fuel/category filters | Third-party scraper, not an alternate source of truth. Inspect code, respect service limits/terms, preserve raw outputs, and reconcile its totals with dashboard exports. The repository's HTTP script sets TLS verification off; correct that before use. [README](https://raw.githubusercontent.com/RevTpark/vahan-scraper/main/README.md) |
| [AutoPunditz car sales](https://www.autopunditz.com/car-sales-figures) | OEM/model wholesale volumes, model trends, new launches, market share | Dispatches are not registrations or taxi purchases; verify every month and scope |
| [AutoPunditz EV sales](https://www.autopunditz.com/electric-vehicle-sales) | EV model/OEM registrations or dispatches, depending on article; powertrain and competition trend | Do not blend sales bases; consumer EV adoption is not cab fleet adoption |
| [Used-Cars-Market-Analysis repository](https://github.com/Premveer-Analytics/Used-Cars-Market-Analysis) | Potential starting point for resale-price feature ideas if its dataset, provenance, India coverage, and licensing check out | A project repository is not a national used-car market dataset. Do not use an unverified sample/project output for residual values, TAM, or fleet replacement rates |
| [Autiqa Lens Pro](https://autiqa.in/lens/pro) | Rich VAHAN history and filtered OEM/state/fuel/forecast tables for market supply and adoption | Still registration data; forecast needs backtest and cannot replace trip or fleet utilization data |

The Vahan scraper README describes browser-download and direct AJAX approaches, exporting registration tables by state/RTO/category/fuel/maker/year. These are extraction conveniences, not validation. The `verify=False` TLS setting in its API implementation is a security defect and should be changed before running it. [Repository README](https://raw.githubusercontent.com/RevTpark/vahan-scraper/main/README.md) · [API script](https://github.com/RevTpark/vahan-scraper/blob/main/scripts/api.py)

## 5. Analysis methods that fit the evidence

| Question | Recommended analysis | Required data | Do not claim |
|---|---|---|---|
| How large is the reachable ride market? | Bottom-up rides × target share × realized fare, by city and segment; low/base/high scenarios | Operator/platform trip counts; distinct purpose tags; fare distributions; city coverage | National TAM from registrations or market-share reports alone |
| Which vehicle models compete for fleet purchases? | Monthly model/OEM registration and wholesale panel; separate supply vs retail; segment and fuel mix | AutoPunditz and VAHAN with measure/source metadata; commercial registration classes | Sales volumes imply ride demand, operator purchasing, or product preference |
| Which cities are moving to EVs? | City/state monthly panel, EV share and growth; forecast benchmarked to seasonal-naive and ETS | Full-history Lens/VAHAN plus monthly market denominator, consistent geography | Holt–Winters output alone establishes 2035 adoption |
| Does a policy cause more EV adoption? | Difference-in-differences/event study only with a defensible treatment/control design; otherwise descriptive interrupted trends | Long pre/post city-state panel, policy timing, controls, policy exposure, parallel-trend evidence | Causal effects from four states or a single before/after chart |
| What use cases cluster naturally? | Exploratory hierarchical clustering of actual city × segment × period cells, sensitivity checked across scaling/distance/linkage and resampling | Repeated observed fares, distance, utilization, booking predictability, downtime, and demand | Five invented archetype rows as a data-driven segmentation |
| What do riders value? | MaxDiff or choice-based conjoint; latent-class choice model if sample supports it | Survey respondents sampled by geography/use case; realistic choice tasks | Use-case preference from OEM sales or five synthetic profiles |
| What vehicle configuration is best? | Weighted decision matrix/AHP or TOPSIS as a transparent engineering trade-off; publish weights and sensitivity | Validated fleet requirements, duty cycles, costs, payload, charging, downtime | Subjective weights as revealed market demand |

For every forecast, use a rolling-origin holdout and compare against a seasonal-naive baseline. For every regression, report observation unit, time span, missingness, sample size, fixed effects, standard errors, and out-of-sample or identification checks. More rows alone do not rescue incorrect measurement or overlapping categories.

## 6. Market logic and positioning: what is and is not supported

The available evidence does **not** prove that airport/premium rides yield the highest operator margin, that street-hail vehicles are a poor E1 fit, or that E1's 200 km/day and 45 kWh pack are validated by market demand. Those are hypotheses to test against realized economics.

The useful next comparison is vehicle × duty-cycle TCO, not an assumed margin ranking:

- Energy/fuel and maintenance cost per *total* kilometre, including deadhead.
- Paid-km utilization and completed rides per shift.
- Charging/refuelling time, charger access, queueing, and uptime.
- Vehicle price, finance rate/down-payment, insurance, tax, battery warranty, and residual value.
- Fare and driver/operator split by trip type, cancellation/no-show, airport fees, and commissions/subscriptions.
- City-level permit and operating constraints.

Airport, corporate, commute, intra-city, intercity, and premium should be represented as separate dimensions. A single ride can be tagged by both purpose and customer type; the analysis must preserve these relationships rather than force five mutually exclusive markets.

## 7. Immediate data plan

1. **Lock the unit:** for the product thesis, specify if the output is ride GMV, operator revenue, addressable fleet vehicles, or annual MACH1 vehicle sales. They require different denominators.
2. **Download Lens Pro tables:** national + state monthly data, ideally city/RTO where reliable; registrations by maker, model, vehicle class, fuel, and year-month. Capture filters, units, row counts, extraction timestamp, and definitions.
3. **Build AutoPunditz panel:** at least 60 monthly periods; keep dispatch, registration, and retail measures separate; preserve source links and raw extracts.
4. **Acquire cab fleet evidence:** transport permits/active fleet where available and anonymized operator fleet counts by city/fuel/model. Registration class alone may over/under-count taxi use.
5. **Acquire trip/operating evidence:** partner with one or more fleets/platforms for anonymized monthly or trip-level data. If unavailable, conduct a documented primary survey of operators and riders; show sample, city coverage, and question wording.
6. **Create a clean city × month × use-case panel:** define non-overlapping trip-purpose fields, missingness rules, consistent fares in real/nominal rupees, and holiday/seasonality fields.
7. **Estimate, validate, and only then size:** calculate current segment rides and fare pools first; derive city serviceable market; estimate vehicle demand from utilization/replacement; forecast only after rolling backtests.

## 8. References consulted

- [Business Standard — Motilal Oswal platform daily ride counts, April 2025](https://www.business-standard.com/companies/start-ups/blusmart-s-shock-exit-leaves-india-s-green-mobility-market-up-for-grabs-125041800827_1.html)
- [Times of India — driver trip count and ₹300 broad fare reference, June 2025](https://timesofindia.indiatimes.com/business/india-business/as-commissions-fall-indias-ride-hailing-firms-test-viability-of-flat-fee-economics/articleshow/122029891.cms)
- [AutoPunditz car sales archive](https://www.autopunditz.com/car-sales-figures)
- [AutoPunditz EV sales archive](https://www.autopunditz.com/electric-vehicle-sales)
- [AutoPunditz sales analysis archive](https://www.autopunditz.com/sales-analysis)
- [VAHAN public dashboard](https://vahan.parivahan.gov.in/vahan4dashboard/)
- [RevTpark Vahan scraper README](https://raw.githubusercontent.com/RevTpark/vahan-scraper/main/README.md)
- [Autiqa Lens Pro data coverage and definitions](https://autiqa.in/lens/data-status)
- [Mordor India Taxi Market report summary](https://www.mordorintelligence.com/industry-reports/india-taxi-market) — useful taxonomy/secondary cross-check only; its market estimates use a proprietary framework and its shares are revenue/value shares unless specified, so not substituted for observed trip counts.
- [Premveer-Analytics used-car project](https://github.com/Premveer-Analytics/Used-Cars-Market-Analysis) — inspected as a candidate secondary input; dataset provenance and scope must be verified before using any output.

---

**Decision:** keep market sizing as a scenario with a transparent formula; remove the old 14.8B 2035 ride headline, the five-row clustering, the n=5 regressions, segment EV shares, and categorical “airport margin / intra-city reject” conclusions. Revisit them only when the required ride, fleet, fare, and operating data exist.
