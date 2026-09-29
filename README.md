# SHEIN Product Data Cleaning & Quality Analysis

## Project Overview

This project focuses on cleaning and preparing SHEIN US Home & Kitchen product listing data for downstream analysis.

The dataset contains raw scraped product information, including product titles, bestseller rankings, prices, sales badges, and discounts. The notebook documents data quality issues and applies justified cleaning strategies to create a structured, analysis-ready dataset.

## Project Objectives

* Inspect raw product listing data and identify data quality issues.
* Detect and remove exact duplicate records.
* Handle missing values based on their business meaning.
* Convert price, discount, and sales information into numeric formats.
* Standardize bestseller ranking information.
* Detect and flag price outliers using the IQR method.
* Create a clean dataset with appropriate data types.
* Document data cleaning decisions and assumptions.

## Dataset

The raw dataset contains 3,719 SHEIN US Home & Kitchen product listings and 6 original columns.

### Original Columns

* `goods-title-link`
* `rank-title`
* `rank-sub`
* `price`
* `selling_proposition`
* `discount`

### Final Cleaned Columns

* `product_title`
* `bestseller_rank`
* `rank_category`
* `price_usd`
* `units_sold_est`
* `has_sales_badge`
* `discount_pct`
* `price_outlier`
* `data_pulled_at`

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook

## Data Cleaning Process

### 1. Data Quality Assessment

* Reviewed column data types, missing values, and unique values.
* Checked price and bestseller rank formats.
* Identified duplicate records and inconsistent labels.

### 2. Duplicate Removal

Removed exact duplicate rows while retaining legitimate product listings that appeared under different categories or rankings.

### 3. Missing Value Handling

Applied column-specific strategies:

* Bestseller rank and category: preserved missing values because products may not have bestseller badges.
* Estimated units sold: preserved missing values when sales badges were unavailable.
* Discount percentage: missing discount tags were interpreted as 0% discount.
* Sales badge availability: created a Boolean indicator.

### 4. Data Type Correction

Converted raw text values into appropriate numeric, Boolean, string, and datetime data types.

### 5. Outlier Detection

Used the Interquartile Range (IQR) method to identify potential outliers in:

* Product prices
* Discount percentages
* Estimated units sold

Price outliers were retained and flagged instead of being automatically removed or capped.

### 6. Final Dataset

Created a cleaned dataset with standardized column names and analysis-ready data types.

## Key Outcomes

* Identified data quality issues in raw product listings.
* Removed exact duplicate records.
* Standardized price, discount, and sales information.
* Preserved meaningful missing values.
* Identified potential price outliers.
* Created a structured dataset for further analysis.

## Project Files

```text
SHEIN-Product-Data-Cleaning/
│
├── SHEIN_Product_Data_Cleaning.ipynb
├── shein_home_kitchen_raw.csv
├── shein_home_kitchen_cleaned.csv
└── README.md
```

## How to Run

1. Clone or download this repository.
2. Install the required Python libraries.
3. Place the raw dataset in the appropriate location.
4. Update the dataset path in the notebook if required.
5. Open the notebook in Jupyter Notebook or Google Colab.
6. Run the cells in sequence.

### Install Dependencies

```bash
pip install pandas numpy matplotlib jupyter tabulate
```

## Limitations

* The dataset represents scraped product listings and may not reflect the complete SHEIN catalogue.
* Estimated sales values are derived from displayed sales badges and are not exact transaction counts.
* Missing bestseller badges do not necessarily indicate poor product performance.
* Outlier detection identifies unusual values but does not automatically establish that they are incorrect.
* The dataset does not contain individual customer purchase records.

## Disclaimer

This project is intended for educational and portfolio purposes. SHEIN is referenced solely to identify the source of the product listing data. This project is not affiliated with or endorsed by SHEIN.

## Author

Manoj Kumar Bais
