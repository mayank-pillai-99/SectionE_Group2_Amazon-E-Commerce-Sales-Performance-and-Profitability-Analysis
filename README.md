# Amazon E-Commerce Sales Performance and Profitability Analysis

## Project Overview

**Sector:** E-Commerce / Online Retail  
**Institute:** Newton School of Technology (Rishihood University)  
**Faculty Name:** Satyaki Das

### Problem Statement

In the highly competitive Amazon marketplace, sellers struggle to identify the specific levers that drive revenue. Without structured analysis, it is difficult to determine if investing in "Sponsored Ads," pursuing a "Best Seller" badge, or lowering prices via "Coupons" yields the highest Return on Investment (ROI).

### Objectives

- Analyze Amazon product data to identify key sales drivers.
- Identify how ratings, price, promotions, and stock affect sales and revenue.
- Provide clear insights and a dashboard for data-driven decision-making.

### Team Members

- **Mayank Pillai** - 2401010268 (Project Lead)
- **Sahil Chand** - 2401020104 (Dashboard Lead)
- **Kunal Vats** - 2401010245 (Analysis Lead)
- **Shaurya Sharma** - 2401010439 (Strategy Lead)
- **Praanshu Ranjan** - 2401010329 (PPT and Quality Lead)
- **Anshu Yadav** - 2401010081 (Data Lead)

---

## Data Dictionary

The dataset is structured at the product level. Below is the dictionary detailing business relevance and cleaning actions taken:

| Column Name           | Business Relevance                               | Cleaning Action Taken                                                      |
| :-------------------- | :----------------------------------------------- | :------------------------------------------------------------------------- |
| **title**             | Product ID: Key for identifying items.           | Deleted blank rows.                                                        |
| **rating**            | Quality Metric: Correlates sentiment with sales. | Deleted rows with missing values to ensure quality data.                   |
| **Sales_Clean**       | Volume Metric: Primary measure of demand.        | Extracted integers (e.g., "2K+" → 2000).                                   |
| **Final_Price**       | Revenue Driver: Critical for financial modeling. | Consolidated 3 columns; Deleted rows where price was missing.              |
| **Estimated_Revenue** | North Star Metric: Ultimate success measure.     | Calculated: `Sales * Price`.                                               |
| **is_best_seller**    | Trust Signal: Influences buyer psychology.       | Filled blanks with "No Badge".                                             |
| **is_sponsored**      | Marketing Efficiency: Measures ad ROI.           | Converted to Binary (1=Sponsored, 0=Organic).                              |
| **in_stock**          | Supply Chain: Operational health metric.         | Created Binary Flag based on "Add to Cart" value. Deleted original column. |
| **free_shipping**     | Logistics: Conversion driver.                    | Converted to Binary (1=Free Ship, 0=Paid).                                 |

---

## Cleaning Notes

The data cleaning and preparation process focused on ensuring statistical significance and analytical agility:

1.  **Stratified Sampling:** A large-scale dataset of Amazon product listings was sampled to ensure representativeness.
2.  **Validation:** Removing duplicates and validating pricing information.
3.  **Feature Engineering:**
    - **Revenue Calculation:** `Revenue = Sales * Price` (Formula: `=IF(ISNUMBER(H2), D2 * H2, 0)`)
    - **Price Waterfall:** Consolidated multiple price columns to prioritize Current Price → Variant Price → Listed Price.
    - **Normalization:** Categorical values (like badges and shipping) were converted to binary flags for analysis.

**Current Dataset File:** `1.Raw_dataset/amazon_products_sales_data.csv`  
**Records:** 10,000 (Random Sample)  
**Time Period:** August 21, 2025 to August 30, 2025

---

## Key Insights

### 1. Quality over Quantity

Products with ratings between **4.5 - 5 stars** generate the highest total revenue. High ratings directly impact customer trust and conversion rates.

### 2. The "Badge" Multiplier

Items with a **"Best Seller" badge** generate approximately **5x to 10x higher revenue** than generic items, proving it is the most valuable asset for a seller.

### 3. Ads Drive Volume

"Sponsored" products show significantly higher unit sales (Volume) but often lower margins. This suggests ads are a vital tool for visibility but should be balanced against per-unit profit.

### 4. Stock & Logistics

- **Stock Availability:** In-stock products contribute to the majority (~76%) of sales. Out-of-stock products present a significant revenue risk.
- **Free Shipping:** Acts as a strong conversion driver and influences pricing strategies.

---

## Dashboard Summaries

The Executive Dashboard was designed to track sales performance and revenue trends.

### KPI Framework

- **Revenue:** `Sales × Price`
- **Avg Rating:** Average of product ratings.
- **Sponsored %:** `Sponsored Items / Total Items`

### View Structure

1.  **Top Section (KPIs):** Displays Total Revenue, Average Revenue, Units Sold, and Revenue From Best Seller.
2.  **Middle Section (Charts):**
    - _Rating vs Revenue:_ Visualizes how 4.0-5.0 rated products dominate sales.
    - _Stock Availability:_ Breakdowns of sales by stock status.
3.  **Bottom Section (Comparisons):**
    - Sponsorship performance (Sponsored vs Organic).
    - Best-seller impact.
    - Coupon and Shipping comparisons.

### Interactive Features

The dashboard includes filters for **Rating, Sponsorship, Stock, Coupons, and Free Shipping**, enabling dynamic drill-down analysis for specific product segments.

---

## Future Scope

- **Time-Based Forecasting:** Perform time-series analysis to predict future demand.
- **Customer Segmentation:** Integrate demographic data for deeper buyer insights.
- **Category Analysis:** Granular performance tracking by specific product categories.

## Conclusion

The project successfully identified that **ratings, sponsorship, stock availability, and "Best Seller" badges** are the primary drivers of revenue on Amazon. The accompanying dashboard provides actionable strategies to optimize these levers for improved visibility and profitability.
