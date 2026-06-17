# Swift Dzire · E85 Fuel Economics Dashboard

A single-file HTML dashboard that analyses fuel economics for a personal vehicle (Swift Dzire, Petrol, 10 years old, 300 km/month, city + highway use) against four alternative fuel types — E85 Flex-Fuel, Diesel, CNG, and Electric — using a 52-record vehicle fuel dataset.

The centerpiece is the **E85 Paradox**: E85 burns cleaner and needs less maintenance, but at current Indian pump prices it is *not* cheaper per km than petrol — this dashboard quantifies exactly how much pricing would need to shift to change that.

![Status](https://img.shields.io/badge/status-complete-2dd4a7) ![Type](https://img.shields.io/badge/type-single--file%20HTML-f5a623) ![Charts](https://img.shields.io/badge/charts-pure%20SVG-3b82f6)

---

## 🔍 What it does

Given a raw CSV of vehicle trips grouped by `Fuel_Type`, the dashboard computes and visualises:

| # | Metric | Formula |
|---|--------|---------|
| 1 | Avg cost/km | `Σ Fuel_Cost_INR ÷ Σ Distance_km` |
| 2 | Avg CO₂/km | `Σ CO2_emitted_kg ÷ Σ Distance_km` |
| 3 | Avg maintenance/km | `Σ Maintenance_Cost_INR ÷ Σ Distance_km` |
| 4 | Avg refuel/recharge time | mean of `Refuel_Recharge_time_min` |
| 5 | Cost/km & maintenance/km by vehicle-age bucket | New (0–2y), Mid-life (3–5y), Aged (6–9y), Old (10+y) |
| 6 | **E85 Paradox** | Pump saving %, running-cost penalty %, break-even pump price |
| 7 | E85 Score /10 | Weighted: cost 4pt, CO₂ 3pt, refuel 2pt, maintenance 1pt |

All aggregates use **weighted averages** (sum of costs ÷ sum of distance) rather than a simple mean of per-row ratios, so vehicles with more recorded distance contribute proportionally more — this avoids skew from short trips with abnormal per-km costs.

## 📊 Dashboard sections

1. **Header** — vehicle, fuel, age, monthly distance at a glance
2. **5 KPI cards** — your cost/km, E85 cost/km, E85 premium vs petrol, E85 break-even price, your monthly fuel spend
3. **Bar chart** — cost/km across all 5 fuels, with hover tooltips
4. **Doughnut chart** — CO₂/km share by fuel, with hover tooltips
5. **Line chart** — cost/km trend across vehicle age (0–12y), with a marker at your car's actual age; dashed segments mark age bands with no recorded data for that fuel
6. **Gauge** — animated E85 Score /10 with a one-line verdict
7. **Fuel comparison cards** — 2 pros, 2 cons, and a "best for" use case per fuel; your selected fuel is glow-highlighted

## 🧮 Key findings for this vehicle profile

| Metric | Value |
|---|---|
| Your fuel cost/km (Petrol) | ₹6.21 |
| E85 cost/km | ₹6.37 |
| E85 running-cost penalty | +2.6% vs petrol |
| E85 pump-price saving | 18.0% (₹82 vs ₹100 per litre) |
| E85 break-even price | ₹79.11/litre |
| E85 Score | 5.68 / 10 |
| Monthly fuel cost (300 km) | ≈ ₹1,863 |

**Takeaway:** E85 is ~18% cheaper at the pump, but its lower mileage erases that saving and adds a small net cost per km. It only becomes cheaper to run than petrol if the price falls to roughly ₹79/L or below — while still offering the lowest CO₂/km and maintenance/km of all five fuels in the dataset.

## 🗂 Dataset

Input: `day17_e85_dataset_optimised.csv` — 52 rows, 9 columns:

```
Fuel_Type, Vehicle_Age_yrs, Distance_km, Fuel_Cost_INR,
CO2_emitted_kg, Maintenance_Cost_INR, Refuel_Recharge_time_min,
Fuel_Price_per_unit_INR, Typical_Mileage
```

Fuel types present: `Petrol (E20)`, `E85 (Flex-Fuel)`, `Diesel`, `CNG`, `Electric (EV)` — roughly 9–11 records each.

> Note: some vehicle-age bands have sparse or zero records for certain fuels (e.g. no "10+ year" Petrol entries exist in this sample). The age-trend line chart marks these as dashed extrapolations rather than presenting them as measured data.

## 🛠 Tech

- **Pure SVG** — bar, doughnut, line, and gauge charts hand-built with `SVGElement` APIs, no chart libraries
- **Vanilla JS** — DOM-based tooltips on hover, animated gauge fill via `stroke-dashoffset` transition
- **CSS** — dark navy (`#0a0f1e`) glassmorphism, backdrop blur, per-fuel color coding (Petrol = blue, E85 = amber, Diesel = grey, CNG = green, EV = purple)
- **No CDN, no dependencies, no build step** — open `e85_dashboard.html` directly in any browser
- Responsive from 375px (mobile) to 1440px (desktop)

To re-run with a different vehicle profile or dataset, swap the CSV and recompute the constants embedded in the `<script>` block (`costPerKm`, `co2PerKm`, `co2Share`, `ageBuckets`), or regenerate by re-running the same aggregation logic against the new data.


*Built as part of an ongoing exploration into single-file, dependency-free data dashboards.*
