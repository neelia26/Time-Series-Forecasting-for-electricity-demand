# Electricity-Demand Data Preprocessing

This folder contains the preprocessing code used to prepare the Electricity Load Diagrams 2011–2014 dataset for the LSTM and Transformer experiments.

## Dataset

The original dataset was obtained from the UCI Machine Learning Repository:

**Electricity Load Diagrams 2011–2014**  
https://doi.org/10.24432/C58C86

It contains electricity readings from 370 clients recorded at 15-minute intervals.

## Preprocessing Steps

The preprocessing pipeline:

1. loads the original dataset using the semicolon separator and decimal comma;
2. converts the timestamp column into a chronological datetime index;
3. selects the study period from 2012 to 2014;
4. identifies clients with consistent electricity readings;
5. removes clients with missing values, negative values or excessive zero readings;
6. converts the 15-minute power readings into hourly energy consumption;
7. aggregates the selected clients into one hourly electricity-demand series;
8. creates chronological training, validation and test partitions;
9. fits the scaler using the training data only;
10. creates 168-hour input windows and 96-hour forecasting targets;
11. creates a previous-week seasonal naïve baseline; and
12. saves the processed data and experiment details.

## Data Partitions

- **Training:** January 2012–December 2013
- **Validation:** January 2014–June 2014
- **Testing:** July 2014–December 2014

The data are divided chronologically to prevent future observations from entering the training data.

## Forecasting Windows

Each forecasting example contains:

- **Input:** previous 168 hours;
- **Target:** following 96 hours.

The seasonal naïve baseline predicts each target hour using the demand observed at the same hour one week earlier.

## Main Output Files

- `system_load_hourly.csv` – cleaned hourly electricity-demand series
- `selected_clients.csv` – clients included in the aggregated series
- `client_metadata.csv` – client-selection information
- `scaler.json` – training-set scaling parameters
- `experiment_details.json` – experimental configuration
- `window_metadata.csv` – timestamps and partition information
- `train/` – training windows
- `validation/` – validation windows
- `test/` – test windows

Each partition may contain:

- `x_raw.csv` – original input values
- `x_scaled.csv` – scaled input values
- `y_raw.csv` – original target values
- `y_scaled.csv` – scaled target values
- `seasonal_naive.csv` – previous-week baseline predictions
- `window_metadata.csv` – timestamps for each window

## Running the Preprocessing

1. Download the original UCI dataset.
2. Place the dataset in the path specified in the preprocessing notebook or script.
3. Run all preprocessing cells in order.
4. Confirm that the processed files are created successfully.
5. Use the same generated files for both the LSTM and Transformer implementations.

## Important Notes

- The scaler is fitted using training data only.
- The same test targets must be used for both models.
- Predictions must be converted back to kWh before evaluation.
- The original dataset should remain unchanged.
- Large processed files may be stored externally instead of being committed to GitHub.
