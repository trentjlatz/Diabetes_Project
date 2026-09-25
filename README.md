# Diabetes_Project

**Status: Work in progress**

The goal of this project is to identify which socioeconomic and demographic characteristics are most associated with diabetes prevalence at the county level.

## Overview

This project began as an investigation into food access and diabetes prevalence. Regression analysis (R-squared = 0.76) found that food access had a statistically significant but practically negligible effect on diabetes rates relative to other factors, with senior population rate and poverty rate emerging as the strongest predictors. As a result, the project has broadened to examine a wider set of socioeconomic and demographic factors, such as income, age, and race, and how they relate to diabetes prevalence. Food access remains part of the analysis, but is no longer the central focus. Analysis and structure are still evolving as the project develops.

Analysis was originally conducted at the census tract level. Since CDC PLACES tract-level estimates are modeled rather than directly measured, and individual tracts can have small underlying populations, tract-level rates can be noisy. Data has since been aggregated to the county level using population-weighted averages, producing more stable estimates and aligning with prior literature on food access and diabetes, most of which is conducted at the county level.

## Data

- **Food Access Research Atlas (USDA)** — tract-level food access data, including proximity to grocery stores, income, and poverty status.
- **CDC PLACES ("Local Data for Better Health")** — tract-level health outcome data, filtered for diabetes-related measures.

Both datasets are collected at the census tract level and aggregated up to the county level as part of processing (see Methods below). Raw data files are not included in this repo. To reproduce locally, download the datasets from their respective sources and place them in `data/raw/` (see file structure below).

## Methods

- Tract-level diabetes prevalence (CDC PLACES) is combined with socioeconomic and demographic indicators from USDA FARA data.
- Tract-level data is aggregated to the county level using population weighted averages, so that larger tracts contribute proportionally more to each county's estimate.
- Regression analysis is used to identify which factors are most strongly associated with diabetes prevalence, with planned interaction effects to test whether relationships differ across income, age, and racial groups.
- Analysis and modeling approach are still being refined as the project develops.

## Repo Structure

```
data/
  raw/         # downloaded source data (not tracked)
  processed/   # cleaned/filtered datasets used in analysis
01_Diabetes_EDA.ipynb        # exploratory data analysis and tract-to-county aggregation
02_Diabetes_Modeling.ipynb   # modeling work
```

## Notes

This is an active project: structure, methodology, and findings may change as work continues.