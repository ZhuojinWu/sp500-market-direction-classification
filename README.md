# S&P 500 Market Direction Classification

A leakage-aware logistic regression case study using daily S&P 500 data from 2014 through 2023.

## Project objective

This project evaluates whether three interpretable, lagged technical indicators can classify daily S&P 500 market direction:

- Previous-day return
- Five-day realized volatility through the previous day
- Prior close relative to its trailing ten-day moving average

The analysis uses a chronological 80/20 train-test split so that future observations never influence model training or feature construction.

## Key result

The model achieved approximately **49.6% accuracy** on the holdout period, below the **51.4% majority-class baseline**. The result shows that these simple technical features do not provide a reliable standalone trading signal. Reporting this limitation is central to the project: strong in-sample fit is not evidence of out-of-sample predictability.

## Repository contents

- `sp500_market_direction.qmd` - reproducible Quarto/R analysis
- `sp500_market_direction_report.pdf` - rendered analytical report
- `sp500_daily_data.csv` - daily market dataset used by the analysis

## Reproduce the analysis

Install [Quarto](https://quarto.org/) and the required R packages:

```r
install.packages(c("tidyverse", "zoo", "broom", "knitr"))
```

Render the report:

```bash
quarto render sp500_market_direction.qmd
```

## Authors

Jayking Wu, Wanxin Zhou, Michelle Xu, and Xinxin Chen

## Disclaimer

This project is for educational and portfolio purposes only and is not financial advice.
