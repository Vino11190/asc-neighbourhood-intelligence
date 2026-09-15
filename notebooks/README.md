# Python Analysis Notebooks

This directory contains the Python/Jupyter Notebook components used to develop the ASC Neighbourhood Intelligence project.

The analytical workflow includes:

- Data loading and inspection
- ONS population data preparation
- Adult Social Care referral data preparation
- LSOA-level data integration
- IMD deprivation integration
- Population-adjusted referral-rate calculation
- Neighbourhood demand analysis
- Inequality analysis
- Monthly demand preparation
- Forecasting preparation
- Export of the integrated dataset for Power BI

## Key analytical measure

Referral Rate per 1,000:

`Referral_Rate_per_1000 = (ASC_Referrals / Population_65_plus) × 1000`

## Recorded analytical outputs

- Total ASC referrals: 1,355
- Highest referral neighbourhood: Southampton 001A
- Highest referral rate: 285.7 per 1,000
- Most deprived vs least deprived referral-rate ratio: 1.34×
- Monthly demand series: approximately 980 → 1,295
- Projected 12-month demand increase: 13.9%

The notebooks form the analytical data-processing layer behind the Power BI dashboard.
