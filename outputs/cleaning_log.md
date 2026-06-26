# Data Cleaning Log

## 1. Issues Found

The following data quality issues were identified during the cleaning process:

* Missing region values
* Missing ship mode values
* Missing discount values
* Exact duplicate records
* Duplicate order IDs with conflicting information
* Negative discount values
* Invalid shipping records where the ship date occurred before the order date
* Cancelled, returned, and failed-payment related records requiring business rule handling
* Differences between calculated and source sales/profit values

---

## 2. Cleaning Actions Performed

The following cleaning actions were completed:

* Standardized date formats for order date and ship date.
* Trimmed and cleaned text fields where necessary.
* Filled missing region values with **"Unknown"**.
* Filled missing ship mode values with **"Unknown"**.
* Replaced missing discount values with **0** when all other sales-related fields were valid.
* Removed **20 exact duplicate rows**.
* Flagged **12 duplicate order IDs** for manual review instead of deleting them.
* Created calculated columns including:

  * cleaned_discount
  * calculated_sales
  * calculated_profit
  * profit_margin
  * shipping_delay_days
  * order_month
  * order_year
  * data_quality_flag

---

## 3. Business Rules Applied

The following business rules were implemented:

* Missing region → Filled with **Unknown**
* Missing ship mode → Filled with **Unknown**
* Missing discount → Replaced with **0** only when other sales fields were valid
* Negative discount → Flagged as invalid
* Discount above allowed range → Checked and flagged if present
* Cancelled orders → Excluded from completed sales summaries
* Failed payments → Excluded from completed sales summaries
* Returned/Refunded orders → Reported separately where applicable
* Ship date before order date → Flagged as an invalid shipping record

---

## 4. Assumptions Made

* Unknown values were used instead of deleting records with missing region or ship mode.
* Blank discounts were assumed to be zero only when the remaining sales information was complete.
* Duplicate order IDs with conflicting information were retained and flagged instead of being removed.
* Calculated sales and profit columns were created independently to validate source data.

---

## 5. Records Removed

* Exact duplicate rows removed: **20**

---

## 6. Records Flagged

* Duplicate order IDs flagged for review: **12**
* Negative discount records: **15**
* Invalid shipping records: **21**
* Sales calculation mismatches: **93**
* Profit calculation mismatches: **40**

---

## 7. Limitations

* Calculated sales and profit did not exactly match all source values because of differences in source calculations and rounding.
* Some business-specific rules could not be fully verified without additional documentation.
* Records flagged for review require manual investigation before making final business decisions.
