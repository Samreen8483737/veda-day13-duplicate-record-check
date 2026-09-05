# Day 13: Duplicate Record Check

## Objective
Understand duplicate detection by finding, documenting, and cleaning duplicate records in a dataset using Python and Pandas.

## Technical Implementation
I utilized Google Colab and the Pandas library to analyze a retail sales dataset for data duplication errors.

1. **Duplicate Detection:**
   * Executed `df.duplicated().sum()` to check for full-row duplicates (exact matches across all columns). **Found: 1**.
   * Executed `df.duplicated(subset=['Order_ID']).sum()` to check for key-column duplicates (e.g., same Order ID, but different item details). **Found: 2**.

2. **Data Cleaning:**
   * Deployed the `df.drop_duplicates()` function to generate a clean, accurate copy of the dataframe.
   * Successfully removed the exact full-row duplicate.
   * Intentionally retained the key-column duplicates (ORD-05), as the differing product columns indicated a valid multi-item order rather than a data entry error.

## Audit Note
* **Action Taken:** Full-row data entry errors were dropped. Key-column duplicates were flagged for business-logic review but retained in the clean dataset to prevent accidental data loss of legitimate split-shipments.
