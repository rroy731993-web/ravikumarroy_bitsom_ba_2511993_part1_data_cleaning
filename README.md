# ravikumarroy_bitsom_ba_2511993_part1_data_cleaning



## Problem Summary

The objective of this project was to clean, validate, and analyze a sales orders dataset. The dataset contained missing values, duplicate records, invalid discounts, shipping date issues, and inconsistent business information. After cleaning, business rules were applied, calculated fields were created, and summary reports were generated to improve data quality and support business analysis.

---

## Dataset Description

The dataset contains sales order information including:

* Order ID
* Order Date
* Ship Date
* Customer Details
* Region
* Category and Sub-category
* Product Information
* Quantity
* Unit Price
* Discount
* Sales
* Cost
* Profit
* Payment Status
* Order Status
* Shipping Mode

Final cleaned dataset size:

* **912 records**
* Duplicate rows removed during cleaning.

---

## Tools Used

* Microsoft Excel
* Pivot Tables
* Excel Functions (IF, COUNTIF, SUM, AVERAGE, MONTH, YEAR, ROUND, etc.)
* Conditional Formatting
* Sorting and Filtering

---

## Cleaning Steps Performed

* Standardized date formats.
* Cleaned text values.
* Filled missing region values with **Unknown**.
* Filled missing ship mode values with **Unknown**.
* Replaced missing discount values with **0** when valid.
* Removed exact duplicate rows.
* Flagged duplicate Order IDs with conflicting information.
* Validated shipping dates.
* Flagged invalid discounts.
* Created calculated columns:

  * cleaned_discount
  * calculated_sales
  * calculated_profit
  * profit_margin
  * shipping_delay_days
  * order_month
  * order_year
  * data_quality_flag

---

## Business Rules Applied

* Missing Region → Filled with **Unknown**
* Missing Ship Mode → Filled with **Unknown**
* Missing Discount → Replaced with **0** when other sales fields were valid
* Negative Discount → Flagged as invalid
* Discount above allowed range → Checked and flagged
* Cancelled orders → Excluded from completed sales summaries
* Failed payments → Excluded from completed sales summaries
* Returned/Refunded orders → Reported separately where applicable
* Ship Date before Order Date → Flagged as invalid shipping record

---

## Summary of Data Quality Issues Found

| Issue                         | Count |
| ----------------------------- | ----: |
| Missing Region                |    25 |
| Missing Ship Mode             |    21 |
| Missing Discount              |    18 |
| Exact Duplicate Rows Removed  |    20 |
| Duplicate Order IDs Flagged   |    12 |
| Negative Discount Records     |    15 |
| Invalid Shipping Records      |    21 |
| Sales Calculation Mismatches  |    93 |
| Profit Calculation Mismatches |    40 |

---

## Summary of Final Pivot Reports

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-category
3. Order Count by Ship Mode
4. Average Profit Margin by Customer Segment
5. Order Status by Region
6. Monthly Sales Trend

Sorting and filtering were applied where required.

---

## Key Business Insights

* South region generated the highest total sales.
* Technology was the highest-performing product category.
* Consumer customers had the highest average profit margin.
* Standard Class was the most frequently used shipping mode.
* Monthly sales varied across 2024 and 2025, with noticeable peak months.
* A number of sales and profit calculation mismatches were identified, indicating that calculated values should be validated against source-system values before reporting.

---

## Assumptions and Limitations

### Assumptions

* Missing region and ship mode values were replaced with **Unknown**.
* Blank discounts were treated as **0** only when other sales-related fields were complete.
* Duplicate Order IDs with conflicting information were retained and flagged for manual review.
* Calculated sales and profit columns were created independently for validation purposes.

### Limitations

* Some calculated values differed from source values due to source calculations or rounding.
* Business-specific validation rules beyond those provided could not be verified.
* Records flagged for review require manual investigation before operational use.

---

## Screenshots Included

The project submission includes screenshots demonstrating:

* Missing value analysis
* Duplicate detection
* Data cleaning process
* Calculated columns
* Data quality report
* Pivot tables
* Final cleaned dataset
