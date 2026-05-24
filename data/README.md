# Dataset Access

The dataset used in this project is not included in this repository due to licensing and ownership restrictions.

## Source

Melbourne Housing Market Dataset (Kaggle)

https://www.kaggle.com/datasets/anthonypino/melbourne-housing-market

## Dataset Description

This dataset contains historical Melbourne housing market data, including:

* Property prices
* Sale dates
* Property types
* Number of rooms
* Distance from CBD
* Regional information
* Land and building area features

The dataset was originally scraped from publicly available listings on Domain.com.au.

## Setup Instructions

1. Download the dataset manually from the Kaggle source above.
2. Extract the CSV file.
3. Rename the dataset file to:

```text
quarterly_prices.csv
```

4. Place the file inside:

```text
data/raw/
```

## Notes

* This repository only contains the forecasting pipeline, notebooks, diagnostics, and generated outputs.
* Users are responsible for complying with Kaggle licensing and dataset usage terms.
* Quarterly aggregation and preprocessing steps are performed within the notebooks/scripts included in this repository.
