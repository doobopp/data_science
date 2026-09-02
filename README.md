# data_science

Binder-ready sandbox for data science experiments focused on Agency RMBS prepayment modeling.

## Binder environment

This repository includes `/home/runner/work/data_science/data_science/environment.yml` with packages for:
- Python data science: `numpy`, `pandas`, `scipy`, `matplotlib`, `plotly`, `statsmodels`, `ISLP`
- R interoperability/modeling: `r-base`, `rpy2`, `r-mgcv` (for spline GAM workflows)

`glm` is available through `statsmodels.api.GLM` (Python) and `stats::glm` (R base).

## Example notebook

Run `/home/runner/work/data_science/data_science/notebooks/rmbs_competing_hazards_example.ipynb` to:
1. Simulate a monthly panel (5 years, 2,000 loans) with competing refinance and buyout hazards
2. Generate features aligned with RMBS intuition:
   - FICO (300-850, mean near 714)
   - Rate incentive with an S-curve relationship to refinance probability
   - LTV (0-1, mean near 0.75)
3. Fit spline-logit submodels for refinance and buyout
4. Aggregate those competing hazards into a global SMM estimate
