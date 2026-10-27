# Carbon Price Exposure Valuation Framework (EU ETS)

Estimates how much future EU carbon prices could cost 22 European firms (Energy, Life Sciences, Transport), and whether firms with climate targets (SBTi) are less exposed.

Built during a consultancy project at Avertim (Brussels), January to February 2026.

## How it works

Monte Carlo GBM  →  DCF model (Excel)  →  Output analysis  →  Power BI

1. `monte_carlo_gbm_simulation.ipynb`: simulates EU carbon prices up to 2035 under three policy scenarios (status quo, Fit for 55, accelerated).
2. `Dynamic_Carbon_Exposure_Model.xlsx`: turns each firm's emissions into future carbon costs and discounts them to a net present value (NPV).
3. `output_analysis.ipynb`: prepares the results for the dashboard.
4. `PowerBI/`: the interactive dashboard (`ModelReport.pbix`) and its data files.

## Note

Emissions are based on public company reports, so results are indicative.

Paulian Oprescu, Wageningen University & Research
