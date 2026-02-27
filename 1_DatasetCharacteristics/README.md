# Dataset Characteristics

**[Notebook](exploratory_data_analysis_CPH2.ipynb)**

## Dataset Information

### Dataset Source
- **Dataset Link:** [Provide a direct link to your dataset. If the dataset is private, explain the reason and provide contact information for the dataset owner]
- **Dataset Owner/Contact:** [If applicable, provide contact information for private datasets]

### Dataset Characteristics
- **Number of Observations:** 10,896 rows
- **Temporal resolution:** daily
- **Panel structure:** 6 products per date (6 products; one-hot encoded as `Product_2`…`Product_6`, with “Product 1” as the all-zeros baseline)
- **Number of Features:** 23 (22 input features)


### Target Variable/Label
- **Label Name:** `Revenue`
- **Label Type:** Regression
- **Label Description:** Continuous revenue value for a given **date × product** row.
- **Label Values (summary):**
  - min=0.00, p25=74.16, median=133.70, p75=262.26, max=1879.46
  - mean=176.84, std=152.23
- **Label Distribution (by product, mean/min/max):**
  - Product 1: mean=122.16, min=23.11, max=416.79
  - Product 2: mean=402.50, min=175.00, max=1203.43
  - Product 3: mean=163.38, min=37.74, max=565.94
  - Product 4: mean=85.36, min=0.00, max=430.50
  - Product 5: mean=276.90, min=121.49, max=1879.46
  - Product 6: mean=10.71, min=0.00, max=172.87

### Feature Description

### Time and index
- **`Date` (datetime):** Calendar date for the observation (daily).
- **`t` (int):** Time index (monotonically increasing day counter within the dataset date span).
- **`Month` (int, 1–12):** Month of year.

### Calendar / event flags (binary: 0/1)
- **`Holiday`:** Indicates whether the date is a holiday.
- **`NextDayHoliday`:** Indicates whether the *next day* is a holiday.
- **`IsWeekend`:** Weekend indicator.
- **`KielerWeek`:** Event indicator for Kieler Woche (Kiel Week) period.
- **`IsNewYearsEve`:** Indicates December 31.
- **`IsHalloween`:** Indicates October 31.

### Lagged / rolling statistics (float)
> These are typical engineered time-series predictors for revenue; values suggest they were computed over a time series (likely per product).
- **`lag_1`:** Previous day value (lag-1) of the target-related series.
- **`roll7_mean`:** 7-day rolling mean.
- **`roll28_mean`:** 28-day rolling mean.

### Seasonal encodings (float, approximately in [-1, 1])
- **`year_sin1`, `year_cos1`:** First-order yearly cyclical encoding (sine/cosine).
- **`year_sin2`, `year_cos2`:** Second-order yearly cyclical encoding (captures higher-frequency seasonality).

### Product identifiers (one-hot; binary 0/1)
- **`Product_2`, `Product_3`, `Product_4`, `Product_5`, `Product_6`:** One-hot product indicators.  
  - **Product 1** is the implicit baseline when all product dummy columns are 0.


## Exploratory Data Analysis

The exploratory data analysis is conducted in the [exploratory_data_analysis_CPH2.ipynb](exploratory_data_analysis_CPH2.ipynb) notebook, which includes:

- Data loading and initial inspection
- Statistical summaries and distributions
- Missing value analysis
- Feature correlation analysis
- Data visualization and insights
- Data quality assessment