# Bengaluru House Price Prediction

A hands-on regression project focused on understanding Bengaluru housing data and building a reproducible house-price prediction workflow.

## Project objective

Explore the dataset, investigate data-quality issues, engineer useful features, train regression models, and evaluate their performance on held-out data.

## Dataset

- **Source:** [Bengaluru House Price Data on Kaggle](https://www.kaggle.com/datasets/amitabhajoy/bengaluru-house-price-data)
- **Shape:** 13,320 rows × 9 columns
- **Target:** `price` (reported in lakhs)
- **Problem type:** Supervised regression

Please review the dataset's licence and terms before redistributing the data. The raw CSV is not committed to this repository.

## Day 1 — Data understanding and initial EDA

### Initial findings

| Finding | Observation |
|---|---:|
| Dataset records | 13,320 |
| Columns | 9 |
| Most common area type | Super built-up Area (65.99%) |
| Missing values in `society` | 5,502 (41.31%) |
| Exact duplicate occurrences reported by `df.duplicated().sum()` | 529 |
| Mean price | 112.57 lakhs |
| Median price | 72 lakhs |
| Maximum price | 3,600 lakhs |

### Visual observations

- The price histogram shows a right-skewed distribution: the mean is greater than the median and the upper-price tail is long.
- The preliminary `total_sqft` versus `price` scatter plot suggests a generally positive association, with substantial variation at similar areas.
- The preliminary scatter plot converted `total_sqft` using `pd.to_numeric(errors="coerce")`; ranges and non-standard unit strings were therefore excluded from that view. This limitation will be addressed during data cleaning.
- Unusual values are candidates for investigation, not automatic deletion.

## Data-quality issues identified

- `total_sqft` is stored as text and includes ranges and non-standard unit formats.
- `size` contains formats such as `2 BHK` and `4 Bedroom`.
- Categorical columns such as `location` have many unique values.
- Missing values and duplicate records require investigation before any removal or imputation.

## Repository structure

- `notebooks/` — notebooks and reproducible analysis
- `images/` — exported plots used in the documentation

See the README files inside those folders for the planned artifacts.

## Current status

**Completed:** dataset loading, initial inspection, missing-value audit, area-type distribution, price histogram, and preliminary area-versus-price scatter plot.

**In progress:** detailed duplicate investigation, `total_sqft` format analysis, and the remaining data-quality audit.

**Not started:** final data cleaning, feature engineering, model training, model evaluation, and deployment.

## Tools

Python, Pandas, NumPy, Matplotlib, and Google Colab.
