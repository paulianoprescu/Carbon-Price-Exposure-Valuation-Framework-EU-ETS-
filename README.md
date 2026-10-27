# Carbon Price Exposure Valuation Framework (EU ETS)

How exposed are European firms to future EU carbon prices, and does a credible climate strategy reduce that exposure?

This framework simulates EU Allowance (EUA) prices under three policy regimes, converts each firm's projected emissions into future carbon costs, and discounts these to a net present value (NPV). The results are presented in an interactive Power BI dashboard, where firms can be compared with competitors in their sector.

Built during a consultancy project in the Sustainability Services team of Avertim (Brussels), January to February 2026.

## Pipeline

```
Monte Carlo GBM  ->  DCF model (Excel)  ->  Output analysis  ->  Power BI dashboard
```

| Step | File | What it does |
|---|---|---|
| 1 | `monte_carlo_gbm_simulation.ipynb` | Simulates EUA prices for 2026 to 2035 with geometric Brownian motion, calibrated on historical prices since 2005, under three regimes: **status quo**, **Fit for 55** and **accelerated** transition. Reports the P25, P50 and P75 price paths. |
| 2 | `Dynamic_Carbon_Exposure_Model.xlsx` | Projects each firm's Scope 1 and 2 emissions based on its SBTi status, multiplies them by the simulated EUA prices, and discounts the resulting carbon costs to an NPV. |
| 3 | `output_analysis.ipynb` | Combines and cleans the results into the tables used by the dashboard. |
| 4 | `powerbi/ModelReport.pbix` | Interactive dashboard: price scenarios, yearly carbon costs and NPV per firm, by regime and percentile. |

## Coverage

22 listed firms in three sectors: Energy (6), Life Sciences (10) and Transport (6).

## Dashboard data (`powerbi/`)

| File | Contents |
|---|---|
| `EUA_price_scenarios_for_PowerBI.xlsx` | Observed EUA prices (2005 onwards) and simulated P25, P50 and P75 paths per regime up to 2035 |
| `carbon_costs.xlsx` | Yearly carbon cost per firm, regime and percentile (2026 to 2035) |
| `npv_results.xlsx` | NPV of carbon costs per firm, regime and percentile, with SBTi status and market capitalisation |
| `ModelReport.pdf` | Static export of the dashboard, for viewing without Power BI |

The `.pbix` file opens in [Power BI Desktop](https://www.microsoft.com/power-platform/products/power-bi/desktop) (free, Windows). The PDF shows the same pages.

## Limitations

Emissions are approximated from firms' public annual sustainability reports rather than from verified carbon accounting data, and GBM assumes constant drift and volatility within each regime. Results are indicative and intended to compare relative exposure between firms, not to forecast exact costs.

## Author

Paulian Oprescu, MSc Sustainable Supply Chain Analytics, Wageningen University & Research

Licensed under the MIT License.
