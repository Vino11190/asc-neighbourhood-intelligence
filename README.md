# ASC Neighbourhood Intelligence

**Adult Social Care Demand, Inequality & Forecasting Analytics**

Python | Power BI | Power Query | ONS Population Data | IMD | Data Integration | Forecasting

## Project Overview

ASC Neighbourhood Intelligence is an end-to-end data analytics portfolio project designed to transform Adult Social Care referral, population, deprivation and monthly demand data into neighbourhood-level intelligence for strategic planning.

The project combines Python-based data preparation and analysis with an interactive Microsoft Power BI dashboard.

The analytical solution was designed to answer questions such as:

- Which neighbourhoods are experiencing the highest Adult Social Care referral pressure?
- How does demand change when neighbourhood population size is taken into account?
- Is ASC demand associated with neighbourhood deprivation?
- How has service demand changed over time?
- What could future demand look like if the observed trend continues?
- How can analytical evidence support neighbourhood-based service planning?

---

# Business Problem

Raw Adult Social Care referral totals do not provide a complete picture of service pressure.

Neighbourhoods have different population sizes and demographic profiles, while socioeconomic conditions may also influence patterns of service demand.

The project therefore combines several analytical perspectives:

**Demand + Population + Deprivation + Time**

to create a more useful neighbourhood intelligence model.

Rather than relying only on raw referral counts, the project calculates population-adjusted referral rates and combines these with deprivation and demand-trend analysis.

---

# Project Objectives

The project was developed to:

- Integrate Adult Social Care referral, population, deprivation and monthly demand datasets.
- Calculate comparable neighbourhood referral rates.
- Identify neighbourhoods experiencing higher ASC demand.
- Analyse differences in demand across deprivation groups.
- Visualise historical service-demand trends.
- Produce a forward-looking demand forecast.
- Translate analytical findings into strategic planning insights.
- Demonstrate an end-to-end public-sector analytics workflow using Python and Power BI.

---

# Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data preparation and analytical processing |
| pandas | Data cleaning, transformation and integration |
| Jupyter Notebook | Reproducible analytical workflow |
| Microsoft Power BI | Interactive dashboards and reporting |
| Power Query | Data transformation and modelling |
| DAX / Power BI Measures | KPI and analytical calculations |
| ONS Data | Neighbourhood population denominators |
| IMD | Deprivation analysis |
| GitHub | Version control and portfolio presentation |

---

# Data Architecture

The analytical workflow combines four main data components:

```text
Adult Social Care Referrals
            |
            v
      LSOA / Neighbourhood
            |
      +-----+-----+
      |           |
      v           v
ONS Population   IMD Deprivation
      |           |
      +-----+-----+
            |
            v
Integrated Neighbourhood Dataset
            |
            v
Referral Rate per 1,000
            |
            +-------------------+
            |                   |
            v                   v
Neighbourhood Analysis    Inequality Analysis

Monthly Demand Data
            |
            v
Time-Series Analysis
            |
            v
Demand Forecast
            |
            v
       Power BI
            |
            v
Strategic Planning Insights
```

---

# Data Sources

## Adult Social Care Sample Data

The ASC sample dataset contains neighbourhood-level referral information used to develop and demonstrate the analytical pipeline.

The portfolio dataset does not represent identifiable resident-level Adult Social Care records.

## ONS Population Data

ONS LSOA 2021 population information was used to provide the population denominator required for neighbourhood comparison.

The project worked with population information from the Mid-2022, Mid-2023 and Mid-2024 LSOA 2021 datasets.

## Index of Multiple Deprivation

IMD data was integrated with the neighbourhood dataset to examine differences in ASC referral demand across deprivation groups.

## Geographic Boundaries

Geographic boundary information supports LSOA and neighbourhood identification and provides the foundation for spatial analysis and potential mapping.

## Monthly Demand

A 24-month monthly referral series was used to examine historical demand and provide the basis for forward-looking forecasting.

---

# Python Analytical Pipeline

The Python implementation is organised into three principal Jupyter notebooks.

## 1. Data Loading and Preparation

[`01_load_data.ipynb`](notebooks/01_load_data.ipynb)

Responsible for the initial loading, inspection and preparation of project datasets.

The workflow includes:

- Loading ASC referral data
- Loading population data
- Inspecting dataset structures
- Preparing geographic identifiers
- Cleaning fields
- Validating data before integration

---

## 2. Neighbourhood Analysis

[`02_neighbourhood_analysis.ipynb`](notebooks/02_neighbourhood_analysis.ipynb)

Performs the main neighbourhood-level analytical processing.

The workflow includes:

- ASC and population integration
- LSOA-level analysis
- Referral-rate calculation
- IMD integration
- Neighbourhood demand comparison
- Deprivation analysis
- Preparation of analytical outputs for Power BI

---

## 3. Demand Forecasting

[`03_demand_forecasting.ipynb`](notebooks/03_demand_forecasting.ipynb)

Supports the demand and forecasting component of the project.

The workflow includes:

- Monthly demand preparation
- Time-series analysis
- Historical trend assessment
- Forecast preparation
- Forward-looking demand analysis

---

# Key Analytical Measure

Raw referrals were converted into a population-adjusted referral rate.

```text
Referral_Rate_per_1000 =
(ASC_Referrals / Population_65_plus) × 1000
```

This makes neighbourhood comparisons more meaningful because differences in the size of the older population are taken into account.

---

# Key Recorded Results

The portfolio analysis produced the following recorded outputs:

| Indicator | Result |
|---|---:|
| Total ASC referrals | 1,355 |
| Highest referral neighbourhood | Southampton 001A |
| Highest referral rate | 285.7 per 1,000 |
| Most deprived vs least deprived referral-rate ratio | 1.34× |
| Historical monthly demand | ~980 → ~1,295 |
| Projected 12-month demand increase | 13.9% |

These values represent outputs from the portfolio analytical dataset and should not be interpreted as current operational council statistics.

---

# Neighbourhood Demand Analysis

Population-adjusted referral rates allow neighbourhood demand to be compared without relying solely on raw referral totals.

The recorded analysis identified:

**Southampton 001A**

as the neighbourhood with the highest referral rate in the portfolio dataset:

**285.7 referrals per 1,000 population aged 65+.**

This type of measure can help analysts identify areas where demand appears disproportionately high relative to the relevant population.

---

# Inequality Analysis

The integrated dataset was analysed using IMD deprivation quintiles.

The recorded analysis found that:

**the most deprived areas had approximately 1.34× the referral rate of the least deprived areas.**

This provides an analytical signal that deprivation and Adult Social Care demand may be associated within the portfolio dataset.

It does **not** establish that deprivation directly causes higher ASC demand.

Additional demographic, health, service-access and population factors would need to be considered before drawing causal conclusions.

---

# Demand & Forecasting

The project includes a 24-month monthly referral series.

Recorded demand increased from approximately:

**980 referrals → 1,295 referrals**

over the historical period.

A forward-looking forecasting view was then developed in Power BI.

The recorded 12-month projection indicated approximately:

**13.9% projected demand growth.**

This forecast is intended as a planning indicator rather than a guaranteed future outcome.

Operational forecasting would require additional validation, backtesting and consideration of seasonality, demographic change, policy changes and service redesign.

---

# Power BI Dashboard

The analytical outputs were transformed into a multi-page Power BI dashboard.

The dashboard focuses on three principal analytical areas.

## Neighbourhood Demand

Provides an overview of:

- Total ASC referrals
- Neighbourhood demand
- Referral rates per 1,000
- Higher-demand neighbourhoods
- Population-adjusted comparisons

![Neighbourhood Demand Dashboard](screenshots/01-neighbourhood-demand.png)

---

## Inequalities Analysis

Examines the relationship between deprivation and Adult Social Care demand.

The page uses IMD quintiles and visual formatting to highlight differences between deprivation groups.

![Inequalities Analysis](screenshots/02-inequalities-analysis.png)

---

## Demand & Forecast

Shows:

- Historical monthly referrals
- Demand trend
- Forecast
- Projected growth
- Forward-looking planning indicators

![Demand and Forecast Dashboard](screenshots/03-demand-forecast.png)

---

# Strategic Insights

The project demonstrates how neighbourhood intelligence can support several strategic planning questions.

### Demand Hotspots

Population-adjusted rates help identify neighbourhoods experiencing comparatively high referral pressure.

### Inequalities

Combining ASC demand with IMD provides evidence for investigating whether more deprived communities experience greater service demand.

### Capacity Planning

Historical trends and forecasts can support discussions about future assessment workload, workforce requirements and service capacity.

### Preventative Services

Neighbourhood-level intelligence can help identify areas where preventative support or earlier intervention may warrant further investigation.

### Integrated Neighbourhood Working

Combining demographic, socioeconomic and service-demand data provides a stronger evidence base for neighbourhood-focused planning.

---

# Data Quality & Troubleshooting

The development process included several practical data and Power BI challenges.

These included:

- Reshaping imported data using Power Query
- Correcting inappropriate aggregation
- Configuring exact KPI display units
- Sorting neighbourhoods by referral rate
- Configuring IMD conditional formatting
- Correcting demand-chart aggregation
- Correcting an erroneous projected-growth calculation
- Aligning the forecast KPI to a 12-month horizon
- Managing notebook execution dependencies
- Correcting time-series date handling

Documenting these issues demonstrates the iterative quality-assurance process involved in developing the analytical solution.

---

# Repository Structure

```text
asc-neighbourhood-intelligence/
│
├── README.md
│
├── docs/
│   ├── README.md
│   └── ASC_Neighbourhood_Intelligence_Complete_Project_Documentation.docx
│
├── notebooks/
│   ├── README.md
│   ├── 01_load_data.ipynb
│   ├── 02_neighbourhood_analysis.ipynb
│   └── 03_demand_forecasting.ipynb
│
├── data/
│   ├── asc/
│   ├── imd/
│   ├── population/
│   └── boundaries/
│
├── powerbi/
│   ├── README.md
│   └── ASC_Neighbourhood_Intelligence.pbix
│
└── screenshots/
    ├── README.md
    ├── 01-neighbourhood-demand.png
    ├── 02-inequalities-analysis.png
    └── 03-demand-forecast.png
```

---

# Project Documentation

Full technical and analytical documentation is available here:

[`ASC Neighbourhood Intelligence — Complete Project Documentation`](docs/ASC_Neighbourhood_Intelligence_Complete_Project_Documentation.docx)

The documentation covers:

- Project definition
- Business objectives
- Data sources
- Data integration
- Analytical methodology
- Power BI development
- Forecasting
- Strategic insights
- Technical implementation
- Troubleshooting
- Data governance
- Limitations
- Portfolio outcomes

---

# Data Governance & Ethics

Adult Social Care data can be highly sensitive.

This portfolio project therefore focuses on neighbourhood-level analytical information rather than identifiable resident records.

A production implementation would require controls including:

- Role-based access
- Data minimisation
- Appropriate retention
- Secure storage
- Disclosure-risk management
- Data-quality monitoring
- Auditability
- Appropriate information governance

Area-level IMD information should also not be interpreted as describing the personal circumstances of every resident within a neighbourhood.

---

# Limitations

This project is a portfolio analytical prototype and not an operational Adult Social Care intelligence system.

Key limitations include:

- Portfolio/sample ASC data rather than live operational case data
- Small-area rates may require statistical suppression or confidence intervals in production
- IMD analysis demonstrates association rather than causality
- Forecast results require further validation before operational use
- Geographic boundaries and population estimates should be version controlled
- Operational implementation would require formal information governance and access controls

---

# Future Enhancements

Potential extensions include:

- Automated data pipelines
- SQL-based analytical warehouse
- Power BI scheduled refresh
- Neighbourhood map visualisation
- Demographic segmentation
- Small-number suppression
- Confidence intervals for referral rates
- Forecast backtesting
- Forecast accuracy metrics
- Scenario modelling
- Drill-through neighbourhood profiles
- Service-capacity modelling
- Automated data-quality monitoring

---

# Skills Demonstrated

This project demonstrates practical experience in:

- Python
- pandas
- Jupyter Notebook
- Data cleaning
- Data transformation
- Multi-source data integration
- ONS data
- LSOA analysis
- Population-normalised metrics
- IMD deprivation analysis
- Inequality analysis
- Time-series analysis
- Forecasting
- Power Query
- Microsoft Power BI
- KPI development
- Data visualisation
- Analytical quality assurance
- Strategic insight generation
- Public-sector analytics
- Adult Social Care analytics
- Technical documentation
- GitHub portfolio development

---

# Portfolio Outcome

ASC Neighbourhood Intelligence demonstrates the development of an analytical solution from raw datasets through:

**Data preparation → Integration → Analysis → Forecasting → Visualisation → Strategic insight**

The project combines technical data-analysis capability with an understanding of how analytical evidence can support public-service planning and neighbourhood-based decision-making.

---

## Disclaimer

This repository is an independent portfolio project created to demonstrate data analytics, Python and Power BI capabilities.

It is not an official council analytical system, and the recorded portfolio outputs should not be interpreted as current operational Adult Social Care statistics.
