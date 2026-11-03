# LSTM and Transformer for Electricity-Demand Forecasting

This repository contains the implementations used to compare LSTM and Transformer models for electricity-demand forecasting.

## Models

- Long Short-Term Memory network (LSTM)
- Time-Series Transformer
- Previous-week seasonal naïve baseline

Both models use the same processed electricity-demand data, input period and prediction period.

## Dataset

The implementations use the **Electricity Load Diagrams 2011–2014** dataset from the UCI Machine Learning Repository:

https://doi.org/10.24432/C58C86

The original 15-minute readings were converted into an aggregated hourly electricity-demand series.

## Experimental Setup

- Input period: previous 168 hours
- Forecast period: following 96 hours
- Training period: 2012–2013
- Validation period: January–June 2014
- Test period: July–December 2014
- Metrics: MAE, RMSE and MAPE

## Repository Contents

- `LSTM_Electricity_Demand_Clean.ipynb` – LSTM implementation
- `Transformer_Electricity_Demand_Clean.ipynb` – Transformer implementation
- `data_preparation.ipynb` – dataset preprocessing
- `outputs/` – metrics and generated figures
- `requirements.txt` – required Python packages

## Running the Notebooks

1. Download the original dataset.
2. Run the data-preparation notebook.
3. Run the LSTM and Transformer notebooks using the processed files.
4. Review the generated metrics and forecasting graphs in the `outputs` folder.

Google Colab with a GPU runtime is recommended for training the Transformer.

## Important Note

The implementations are methodology-based adaptations of the selected historical studies. They are not exact reproductions because the original papers used different datasets, configurations and optimisation procedures.
