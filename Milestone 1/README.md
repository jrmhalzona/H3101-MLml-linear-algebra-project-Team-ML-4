# Milestone 1: ML Solution EDA

This folder contains the files prepared for **Milestone 1**. It includes the original datasets, final cleaned datasets, and the Python notebook used for data cleaning and basic data analysis.

## Final Dataset Check

The three final datasets were checked after cleaning.

| Dataset                   |  Rows | Columns | Duplicate Rows | Missing Values |
| ------------------------- | ----: | ------: | -------------: | -------------: |
| Customer Demographics     | 3,023 |       6 |              0 |              0 |
| Customer Transactions     | 3,015 |       6 |              0 |              0 |
| Social Media Interactions | 3,020 |       6 |              0 |              0 |

The final check shows that all three datasets have **0 duplicate rows and 0 missing values**.

## Files and Folders

### 1. Raw Data

The **Raw Data** folder contains the original datasets before cleaning.

It includes:

* `customer_demographics_contaminated.csv`
* `customer_transactions_contaminated.csv`
* `social_media_interactions_contaminated.csv`

These files were used as the starting point for the preprocessing work.

### 2. Final Cleaned Data

The **Final Cleaned Data** folder contains the final versions of the datasets that should be used for **Milestone 1**.

It includes:

* `finmark_customer_demographics_cleaned_final.csv`
* `finmark_customer_transactions_cleaned_final.csv`
* `finmark_social_media_interactions_cleaned_final.csv`

These are the **official final datasets for Milestone 1**.

### 3. Preprocessing Code

The **Preprocessing Code** folder contains:

* `finmark_preprocessing_final.ipynb`

The notebook contains the Python code used to:

* Load the original datasets
* Check the data
* Find duplicate rows
* Check missing values
* Clean incorrect or unusual values
* Prepare the final datasets
* Calculate basic statistics
* Create simple graphs
* Check the final cleaned datasets

The notebook also contains copies of cleaned datasets created during the preprocessing process. These should not be confused with the official files in the **Final Cleaned Data** folder. The official files to use for Milestone 1 are the three files in **Final Cleaned Data**.

## About the Week 3 Files

There are also files with **"cleaned"** in their filenames inside the **Week 3 Preprocessing Submission** folder.

Those files were cleaned during the earlier Week 3 preprocessing work and can be considered **earlier/draft cleaned versions**.

They are kept in the Week 3 folder because they belong to the Week 3 submission.

For **Milestone 1**, please use the files in:

**Milestone 1 → Final Cleaned Data**

Do not confuse the earlier Week 3 cleaned files with the final Milestone 1 datasets.

### Simple guide

| Location                          | What it is for                                         |
| --------------------------------- | ------------------------------------------------------ |
| `Week 3 Preprocessing Submission` | Earlier Week 3 work and cleaned/draft files            |
| `Milestone 1/Raw Data`            | Original datasets before cleaning                      |
| `Milestone 1/Final Cleaned Data`  | **Official final datasets for Milestone 1**            |
| `Milestone 1/Preprocessing Code`  | Python notebook showing the cleaning and analysis work |

## Main Cleaning Work

The preprocessing included:

* Removing duplicate rows
* Handling missing values
* Converting numerical values into the correct format
* Handling unusual age values
* Handling invalid transaction amounts
* Keeping `Unknown` when information was missing and could not be safely guessed
* Making date formats consistent
* Checking the final datasets after cleaning

## Important Note

The **Final Cleaned Data** files are the official datasets to use for Milestone 1.

The numbers and results in the Milestone 1 report should be based on these final datasets and the results shown in the preprocessing notebook.

The folders are organized so that the original data, final cleaned data, and Python notebook can be easily found and reviewed by the team and mentor.
