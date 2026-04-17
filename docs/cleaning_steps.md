# Data Cleaning Steps

Based on an inspection of the data, the following cleaning steps were identified and performed to ensure data quality and consistency.

## 1. Header Standardization

The first row of the table was promoted to serve as the column headers: `ProductName`, `Price`, `Rate`, `Review`, and `Summary`. Data types were then initialized for further processing.

## 2. Handling Corrupted Records

A small number of rows, specifically 4 records, were identified as corrupted because the `Rate` column contained product names or invalid characters such as `s` instead of numeric values. These rows were removed to prevent errors during analysis.

## 3. Data Type Conversion

- `Price` was converted from text to a numeric format to support financial calculations.
- `Rate` was converted to a numeric format after removing corrupted text entries, and the ratings were verified to remain within the standard 1 to 5 range.

## 4. Missing Value Treatment

Rows with missing values in the `Review` or `Summary` columns were removed. There were 8 such instances in total: 3 missing reviews and 5 missing summaries.

## 5. Text Normalization and Cleanup

- Leading and trailing whitespace was stripped from all text columns: `ProductName`, `Review`, and `Summary`.
- The data contains several encoding artifacts such as `??` and other malformed symbols in the `ProductName` and `Summary` columns, likely representing emojis or special symbols. These were preserved to maintain the original sentiment, but they were noted as potential targets for further regex-based cleaning if needed for text mining.

## Summary of Data Changes

- Promoted the first row to headers and standardized column names.
- Removed 4 corrupted records from the dataset.
- Converted `Price` and `Rate` into analysis-friendly numeric formats.
- Removed 8 rows with missing `Review` or `Summary` values.
- Trimmed extra whitespace from text fields while preserving original special-character sentiment artifacts.
