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
  - Risk-reduction (timing) strategy

Daily U.S. Treasury yields (1Y, 2Y, 5Y, 10Y) from FRED are used with an expanding-window out-of-sample evaluation.

## Repository Structure
```text
data/        # Yield data
models/      # Trained models
notebooks/   # Analysis notebooks


## Setup

git clone <repository-url>
cd <repository-name>
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
