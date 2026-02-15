# Amazon Product Sales Data Analysis

## Project Overview

This project contains a comprehensive analysis of Amazon product sales performance data collected in August 2025. The dataset includes detailed information about product ratings, reviews, pricing, and sales velocity indicators ("bought in last month"), providing insights into consumer behavior and product performance trends.

**Note:** This dataset is a **random sample of 10,000 records** from the original larger dataset, ensuring a representative distribution across the collection period.

## Dataset Information

- **Total Records:** 10,000 data points
- **Time Period:** August 21, 2025 to August 30, 2025
- **Number of Unique Products:** 2,568 unique product titles
- **Domain:** E-commerce (Electronics, Office Supplies, Accessories)

## Directory Structure

```
├── 1.Raw_dataset/          # Original processed data (10k sample)
├── 2.Cleaned_dataset/      # Cleaned and processed data
├── 3.Calculation_pivot_table/  # Statistical calculations and analysis
├── 4.Dashboard/            # Dashboard-ready data
├── 6.Presentation/         # Presentation materials
└── README.md               # Project documentation
```

## Column Specifications and Statistical Analysis

### 1. Title (Product Name)

- **Type:** Categorical / Text
- **Total Rows:** 10,000
- **Unique Values:** 2,568
- **Empty Cells:** 0
- **Note:** High duplication (approx. 3.9 records per product) indicates time-series tracking.

### 2. Rating

- **Type:** Numeric (Float)
- **Mean:** 4.40 out of 5
- **Median:** 4.50
- **Empty Cells:** 250 (2.5%)

### 3. Number of Reviews

- **Type:** Numeric (Integer)
- **Total Reviews (Sum):** 32,178,934
- **Mean:** 3,300
- **Max:** 645,416
- **Empty Cells:** 250

### 4. Bought in Last Month (Sales Velocity)

- **Type:** Categorical / Text
- **Unique Values:** 44
- **Top 5 Values:**
  1. "100+ bought in past month": 2,036 records
  2. "50+ bought in past month": 1,375 records
  3. "200+ bought in past month": 1,280 records
  4. "No featured offers available": 1,060 records
  5. Missing/Blank: 802 records
- **Empty Cells:** 802

### 5. Current / Discounted Price

- **Type:** Numeric (Currency)
- **Mean:** $211.36
- **Median:** $71.89
- **Range:** $2.99 - $4,699.00
- **Empty Cells:** 2,701 (27.0%)
- **Insight:** Consistent with the full dataset, ~27% of records lack current price data.

### 6. Listed Price

- **Type:** Numeric (Currency)
- **Mean:** $205.31
- **Empty Cells:** 0

### 7. Is Best Seller

- **Type:** Categorical
- **Distribution:**
  - No Badge: 9,572
  - Amazon's Choice: 161
  - Best Seller: 65

### 8. Is Sponsored

- **Type:** Categorical
- **Distribution:**
  - Organic: 8,332 (83.3%)
  - Sponsored: 1,668 (16.7%)

### 9. Delivery Details

- **Type:** Categorical / Text
- **Top Promise:** "Delivery Mon, Sep 1" (1,452 records)

### 10. Sustainability Badges

- **Type:** Categorical
- **Count of Non-Null:** 770
- **Top Badges:**
  - Small Business: 295
  - Carbon impact: 178
  - Works with Alexa: 108

## Key Findings & Data Quality

1.  **Representative Sample:** The 10k random sample maintains similar statistical properties (means, distributions) to the original 42k dataset.
    - Mean Rating: 4.40 (Same)
    - Sponsored Ratio: ~16.7% (vs 16.4%)
    - Price Missingness: ~27% (Same)
2.  **Discount Strategy:** Approximately **29.0%** of the records show a discounted price (Current < Listed).
3.  **Data Completeness:** High quality for core metrics (Title, Listed Price), with expected missingness in specific features like Badges and Current Price.

## Data Processing Pipeline

1.  **Sampling:** Random selection of 10,000 rows from the original 42,675 record dataset.
2.  **Cleaning:**
    - Parsing currency fields.
    - Standardizing Date formats.
3.  **Analysis:** Statistical profiling performed on the sampled subset.
