# Nigerian Average Food Prices Analysis & Forecasting

Exploratory data analysis and time-series forecasting of monthly average food prices in Nigeria using pandas, matplotlib/seaborn, and Facebook Prophet.

## Overview

This notebook analyzes national average prices for key food items:

- Beans (brown, sold loose)
- Beef (boneless)
- Frozen chicken
- Gari (white, sold loose)
- Rice (imported high quality, sold loose)
- Titus (frozen)
- Tomato
- Yam tuber

The dataset contains 77 monthly observations starting from January 2017.

## Key Steps

1. **Data loading & inspection**
   - Load CSV and examine structure with `.head()`, `.describe()`, and `.info()`
   - Set `Date` as the index
   - Rename columns to shorter, cleaner names (Beans, Beef, Chicken, Garri, Rice, Titus, Tomato, Yam tuber)

2. **Exploratory analysis**
   - Histogram of beans prices
   - Box plots for distribution overview
   - Basic statistical summary

3. **Time-series forecasting**
   - Forecast generated with Prophet
   - Visual comparison of actual vs forecasted values
   - Evaluation metrics calculated on the hold-out period

## Results (Forecast Performance)

| Metric | Value    |
|--------|----------|
| MAE    | 105.37   |
| MSE    | 24030.69 |
| RMSE   | 155.02   |
| MAPE   | 16.82%   |

## Requirements

```bash
pip install pandas numpy matplotlib seaborn prophet
```

## Usage

1. Place the data file `NAVGFood_Prices - NAVGFood_Prices.csv` in the same directory as the notebook.
2. Open and run `Foodprice.ipynb` in Jupyter or Google Colab.

```python
# Example loading step
df_food = pd.read_csv("NAVGFood_Prices - NAVGFood_Prices.csv")
df_food = df_food.set_index('Date')
```

## Data

The dataset appears to contain Nigerian national average food prices (likely sourced from official statistics or market monitoring reports). Prices are monthly averages.

## Notes

- Date parsing may be needed depending on the CSV format (`pd.to_datetime` recommended).
- Column names were cleaned for easier analysis.
- The forecasting section evaluates model performance with standard regression metrics (MAE, MSE, RMSE, MAPE).

## License

This analysis is for educational/demonstration purposes. Check the original data source for any usage restrictions.
