# Time Series Price Forecasting

End-to-end time series forecasting pipeline using SARIMAX and Prophet with quarterly seasonality modeling, temporal validation, and statistical diagnostics.

---

# Project Overview

This project explores statistical time series forecasting techniques on Australian housing market data using:

* **SARIMAX**
* **Prophet**

The primary objective is to forecast quarterly housing prices while analyzing:

* seasonal behavior
* trend structure
* residual characteristics
* temporal dependencies
* exogenous variable effects

The project emphasizes practical forecasting under real-world constraints, including limited feature availability, imperfect stationarity, and computational limitations.

---

# Problem Statement

Forecasting housing prices is inherently difficult due to:

* market volatility
* changing economic conditions
* seasonal cycles
* limited explanatory variables
* temporal dependence structures

This project investigates whether classical statistical forecasting approaches can produce reliable quarterly forecasts using a constrained real-world dataset.

---

# Dataset

The project uses the Melbourne Housing Market dataset from Kaggle.

Dataset access instructions are available in:

```text
data/README.md
```

The dataset itself is not redistributed in this repository due to ownership and licensing restrictions.

---

# Models Used

## 1. SARIMAX

Seasonal AutoRegressive Integrated Moving Average with Exogenous Variables was used to model:

* trend
* seasonality
* temporal autocorrelation
* external regressors

### Exogenous Variables

* Property type
* Bedroom count

### Seasonal Structure

Quarterly seasonality was identified within the data:

```text
S = 4
```

Parameter selection was guided using:

* ACF analysis
* PACF analysis
* residual diagnostics

---

## 2. Prophet

Prophet was used as a comparative forecasting framework due to its:

* automated trend handling
* seasonality decomposition
* robustness to noisy temporal data

---

# Methodology

The forecasting pipeline includes:

* Data preprocessing
* Temporal aggregation
* Stationarity analysis
* Seasonal decomposition
* ADF testing
* ACF/PACF diagnostics
* TimeSeriesSplit validation
* Residual diagnostics
* Ljung-Box testing
* Forecast evaluation

---

# Results

| Model   | Approximate MAPE |
| ------- | ---------------- |
| SARIMAX | ~10.75%          |
| Prophet | ~9.40%           |

Both models produced practically useful quarterly forecasts despite the dataset exhibiting difficult variance behavior and imperfect stationarity.

---

# Key Challenges

## Persistent Variance Instability

Even after:

* differencing
* logarithmic transformations

the series retained difficult variance characteristics.

Instead of over-processing the data, model selection relied primarily on:

* ACF/PACF structure
* forecast behavior
* residual diagnostics

---

## Computational Constraints

SARIMAX retraining is computationally expensive.

Due to local hardware limitations:

* TimeSeriesSplit folds were intentionally limited
* emphasis was placed on statistical interpretability and diagnostics rather than exhaustive hyperparameter searches

---

# Initial Modeling Mistake and Correction

During the initial implementation, exogenous variables were handled similarly to conventional tabular machine learning features.

After reviewing SARIMAX assumptions more carefully, the pipeline was revised to ensure exogenous regressors were treated as temporally aligned explanatory sequences rather than generic feature matrices.

This correction improved the conceptual consistency of the forecasting workflow and reinforced the distinction between:

* classical machine learning pipelines
* statistical time series forecasting systems

---

# Repository Structure

```text
time-series-price-forecasting/
│
├── data/
├── notebooks/
├── outputs/
├── src/
├── README.md
|__ requirements.txt
```

---

# Reproducibility

## Clone Repository

```bash
git clone https://github.com/your-username/time-series-price-forecasting.git

cd time-series-price-forecasting
```

---

## Install Dependencies

Using pip:

```bash
pip install -r requirements.txt
```
---

## Run Jupyter Notebooks

```bash
jupyter notebook
```

---

# Future Improvements

Potential future enhancements include:

* Walk-forward validation
* Hyperparameter optimization
* Additional macroeconomic regressors
* Forecast confidence interval analysis
* Automated SARIMAX tuning
* Probabilistic forecasting
* Dashboard deployment

---

# Technologies Used

* Python
* Pandas
* NumPy
* Statsmodels
* Prophet
* Scikit-learn
* Matplotlib
* SciPy
* Jupyter Notebook

---

# License

This project is intended for educational and research purposes.
