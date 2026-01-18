# Yield Curve Forecasting

This repository contains the code and materials for a bachelor’s thesis in economics and business administration.
The project compares **econometric** and **machine-learning** models for **short-horizon U.S. Treasury yield curve forecasting**, evaluating both **statistical accuracy** and **economic value**.

## Models
- Random Walk (RW)
- Dynamic Nelson–Siegel (DNS)
- Ridge Regression
- XGBoost

## Evaluation
- **Statistical accuracy**
  - RMSE
  - Diebold–Mariano tests
- **Economic value**
  - Long–short trading strategy
  - Risk-reduction simulation

Daily U.S. constant maturity Treasury yields 2Y, 5Y, 10Y from FRED are used with an expanding-window out-of-sample evaluation.

## Repository Structure
```text
.
├── data/                         # Raw U.S. Treasury yield data (FRED)
│   ├── DGS1.csv                  # 1-year yield (short rate)
│   ├── DGS2.csv                  # 2-year yield
│   ├── DGS5.csv                  # 5-year yield
│   └── DGS10.csv                 # 10-year yield
│
├── models/                       # Serialized model outputs (.pkl)
│   ├── RW.pkl                    # Random Walk benchmark (predictions & actuals)
│   ├── DNS.pkl                   # Diebold–Li model outputs
│   ├── Ridge.pkl                 # Ridge regression outputs
│   └── XGBoost.pkl               # XGBoost outputs
│
├── notebooks/                    # Jupyter notebooks (analysis workflow)
│   ├── 01_models.ipynb           # Load and merge data, set up and train RW, DNS, Ridge and XGBoost, produce OOS forecasts
│   ├── 02_forecast_eval.ipynb    # Use results from 01 to create RMSE result table, DM Test table and Robustness Test for RMSE results
│   └── 03_economic_eval.ipynb    # Use results from 01 to perform long-short trading strategy and risk-reduction simulation, perform robustness check on risk-reduction result
│
├── README.md                     # Project overview and replication guide
└── requirements.txt              # Python dependencies

```

## Setup

```text
#Please make sure that you have Python version 3.10 or higher installed
git clone https://github.com/chris-room13/yield-curve-forecasting
cd <your-saved-location> 
python -m venv venv #or python3 -m venv venv if you have another version
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
# Now just select the venv as jupyter kernel
```
Now you can run the individual Notebooks. Make sure to run the cells **in order** to avoid having wrong variables or dependencies. Depending on your setup it can take up to 10 hours for Hyperparameter tuning and model training to be completed. Therefore my training results are saved in the /models folder and you can directly run notebook 02 or 03.
