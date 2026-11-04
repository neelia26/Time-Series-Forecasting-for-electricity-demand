# Electricity Demand Forecasting — Historical Comparison & Data Preprocessing

## Overview

This repository contains the historical forecasting methodology comparison and data preprocessing work conducted as part of the **Time-Series Forecasting for Electricity Demand** project.

The work focuses on two main components:

1. **Historical Comparison:** Investigating and comparing forecasting approaches, particularly Long Short-Term Memory (LSTM) and Transformer-based models, to understand the evolution of electricity demand forecasting methodologies.
2. **Data Preprocessing:** Preparing electricity consumption data for consistent model training, validation, testing, and forecasting experiments.

## 1. Historical Comparison

The historical comparison investigates forecasting methodologies and their application to electricity demand prediction.

### Objectives

- Examine the characteristics of LSTM and Transformer-based forecasting approaches.
- Compare their forecasting performance using consistent evaluation procedures.
- Investigate their strengths, limitations, and suitability for electricity demand forecasting.
- Establish a foundation for subsequent forecasting experiments.

### Implementation

The historical comparison experiments are implemented using **Jupyter Notebooks (`.ipynb`)**.

These notebooks contain the relevant experimental code, model configurations, evaluation procedures, and generated results.

**Note:** Separate comparison output files are not included in this repository. Results and visualisations can be inspected within the notebooks, where saved, or reproduced by executing the relevant notebook cells.

## 2. Data Preprocessing

The data preprocessing stage prepares the electricity consumption dataset for forecasting experiments.

### Objectives

- Clean and organise historical electricity demand records.
- Prepare hourly electricity demand data.
- Apply the required preprocessing and scaling procedures.
- Create training, validation, and testing datasets.
- Construct input-output windows for time-series forecasting.
- Generate baseline forecasts for subsequent model evaluation.

### Forecasting Configuration

| Parameter | Configuration |
|---|---|
| Forecasting task | Electricity demand forecasting |
| Temporal resolution | Hourly |
| Input window | 512 hours |
| Forecast horizon | 96 hours |
| Historical period | 2012–2014 |
| Dataset partitions | Training, validation, testing |
| Baseline | Seasonal Naive |

### Processed Data

The `electricity_processed_data/` directory contains the processed datasets and supporting metadata.

Key files include:

- `hourly_demand.csv` — Processed hourly electricity demand records.
- `system_load_hourly.csv` — Hourly system-level demand.
- `hourly_clients.parquet` — Hourly client-level data.
- `window_metadata.csv` — Metadata describing forecasting windows.
- `train/` — Training inputs, targets, scaled values, baseline forecasts, and window metadata.
- `validation/` — Validation data.
- `test/` — Testing data.

The training directory includes files such as `x_raw.csv`, `x_scaled.csv`, `y_raw.csv`, `y_scaled.csv`, and `seasonal_naive.csv`.

## 3. Reproducibility

### Historical Comparison

Open the relevant `.ipynb` notebooks using Jupyter Notebook, JupyterLab, or Visual Studio Code.

Execute the notebook cells in the intended order to reproduce the experiments, subject to the required datasets, dependencies, and runtime environment being available.

### Data Preprocessing

The processed datasets are provided under `electricity_processed_data/`.

These files support subsequent forecasting experiments and allow the prepared data to be reused without repeating every preprocessing operation.

## 4. Repository Notes

- Historical comparison implementations and available results are maintained in Jupyter Notebooks.
- Separate historical comparison output files are not provided.
- Processed electricity demand datasets are maintained in the `electricity_processed_data/` directory.
- Large dataset files may be managed using Git Large File Storage (Git LFS).

## 5. Project Purpose

Together, the historical comparison and preprocessing components provide a foundation for evaluating electricity demand forecasting methodologies under a consistent experimental framework.

The historical comparison examines the development and performance of forecasting approaches, while the preprocessing stage prepares structured datasets for subsequent model development and evaluation.
