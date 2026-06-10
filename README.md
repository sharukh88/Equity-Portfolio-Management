# Equity Portfolio Management

Simulated management of a $5M equity portfolio in R using 2018 historical daily price data for 10 major tech stocks. The project implements rule-based rebalancing strategies (rather than ML-based ones), tracks dividends, benchmarks performance against a custom "High-Tech Index," and converts returns to JPY.

## Universe

10 major tech stocks, daily data for 2018:

`IBM, MSFT, GOOG, AAPL, AMZN, META, NFLX, TSLA, ORCL, SAP`

## What it does

- **Initial portfolio**: Starts with $5,000,000, buying an initial position across 5 of the 10 stocks on the first trading day of 2018 (Jan 2, 2018).
- **Rebalancing strategies**: Every 5 trading days, the portfolio is rebalanced using one of two rule-based strategies:
  - **Buy Low**: Adds to positions in stocks that have dropped in price.
  - **Buy High**: Adds to positions in stocks that have risen in price (momentum-style).
- **Dividend tracking**: Dividends received are tracked and reinvested/accounted for over the simulation period.
- **Benchmarking**: Portfolio performance (mark-to-market value over time) is benchmarked against a custom High-Tech Index built from the same universe.
- **Currency conversion**: USD returns are converted to JPY using historical USD/JPY exchange rates.

## Repo contents

| File | Description |
| --- | --- |
| `Midterm Project.ipynb` | Main R notebook with data loading, portfolio simulation, rebalancing logic, and performance plots |
| `aapl.csv`, `amzn.csv`, `goog.csv`, `ibm.csv`, `meta.csv`, `msft.csv`, `nflx.csv`, `orcl.csv`, `sap.csv`, `tsla.csv` | 2018 historical daily price data per stock (Yahoo Finance) |
| `usdjpy.csv` | 2018 historical USD/JPY exchange rate data |

## Requirements

- R with the following packages: `data.table`, `dplyr`, `lubridate`, `tidyr`, `ggplot2`, `grid`, `gridExtra`, `gtable`, `plotly`, `purrr`
- Jupyter with an R kernel (e.g. [IRkernel](https://irkernel.github.io/)) to run the notebook

## Running it

1. Clone the repo and open `Midterm Project.ipynb` in Jupyter (with an R kernel).
2. Run the cells in order: data loading → portfolio initialization → rebalancing strategies → benchmarking → currency conversion → plots.

## Data source

Historical daily price data was downloaded from [Yahoo Finance](https://finance.yahoo.com/) for the 2018 calendar year.
