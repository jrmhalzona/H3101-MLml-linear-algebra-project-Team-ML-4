# Beginner Guide: Our Data Cleaning Process

This guide explains **what Jeremiah did first, what Angel did afterward, and what the team should do for Milestone 1**.

You do not need to know much coding to understand it.

---

## 1. What Jeremiah Did First

Jeremiah did the **first round of cleaning**.

He:

* Removed duplicate rows.
* Cleaned some text formatting.
* Checked for blank/missing values.
* Changed blank values into **`Unknown`**.

At first, he used `Unknown` for **both words and numbers**.

For example:

| Gender  |     Age |
| ------- | ------: |
| Female  |      25 |
| Male    |      32 |
| Unknown |      40 |
| Female  | Unknown |

This was useful for seeing which information was missing, but there was a problem with using `Unknown` for numerical columns.

---

# 2. What Angel Did Next

Angel reviewed Jeremiah's cleaned datasets and did the **final cleaning and checking**.

The main thing Angel changed was:

> **Words/categories and numbers need to be handled differently.**

### For words/categories

If we don't know the category, we keep:

**`Unknown`**

Examples:

* IncomeLevel → `Unknown`
* ProductCategory → `Unknown`
* Platform → `Unknown`
* Sentiment → `Unknown`

We don't guess the missing category.

### For numbers

If something should be a number but is missing or invalid, we first treat it as:

**`NaN`**

Think of `NaN` as:

> **"There is no valid number here."**

This is important because Python needs numerical columns to contain numbers if we want to calculate statistics or create numerical graphs.

---

# 3. Why `Unknown` Caused Problems With Graphs

This is one of the most important things to understand.

If a column such as **Age** contains:

```text
25
30
Unknown
45
50
```

Python may treat the column as **text** because `Unknown` is a word.

That can cause problems when we try to:

* calculate the average
* calculate the median
* calculate standard deviation
* create a histogram
* create a boxplot
* analyze the numerical distribution

So Angel changed the approach for numerical columns:

**Missing/invalid number → `NaN` → handle it properly**

For example:

```text
25
30
NaN
45
50
```

Now Python understands that this is a **numerical column with one missing value**.

---

# 4. What Happened to the Missing Numbers?

Angel did not leave the `NaN` values in the final numerical data.

They were handled properly.

### Age

Some ages were:

* missing/`Unknown`
* below 18
* above 70

These were treated as invalid/missing.

The valid ages were checked, and the median was:

**45**

The missing/invalid ages were then filled using 45.

### Transaction Amount

Some amounts were:

* `Unknown`
* `Free`
* negative values such as `-100`

We handled them appropriately:

* `Free` → **0**
* `Unknown` → treated as missing/invalid
* negative values → treated as invalid
* missing/invalid amounts → filled using the median valid amount

Median amount:

**498.015**

---

# 5. Simple Difference Between `Unknown` and `NaN`

### `Unknown`

Used mainly for **categories/words**.

It means:

> "We don't know this information."

Example:

`IncomeLevel = Unknown`

### `NaN`

Used temporarily for **numerical data**.

It means:

> "This should be a number, but there is no valid number here."

Example:

`Age = NaN`

The `NaN` values are then handled so the final numerical column contains proper numbers.

---

# 6. Jeremiah vs. Angel

|                  | Jeremiah                       | Angel                                                        |
| ---------------- | ------------------------------ | ------------------------------------------------------------ |
| Main job         | First cleaning                 | Final cleaning and verification                              |
| Duplicates       | Removed                        | Checked again                                                |
| Blank categories | Changed to `Unknown`           | Kept `Unknown`                                               |
| Blank numbers    | Initially changed to `Unknown` | Changed to `NaN` temporarily and handled properly            |
| Age              | First cleaning                 | Invalid ages handled; median **45** used                     |
| Amount           | First cleaning                 | `Free` → 0; invalid amounts handled; median **498.015** used |
| Final check      | Initial cleaned data           | Final datasets verified                                      |

---

# 7. The Three Versions of the Data

We have **three stages** for each dataset.

### 1. Raw Dataset

The original data.

Use this if you want to see:

* what the data looked like before cleaning
* duplicates
* missing values
* original problems

### 2. Jeremiah's Cleaned Dataset

The **first cleaned version**.

Use this if you want to understand Jeremiah's first cleaning work.

### 3. Angel's Final Cleaned Dataset

The **official final version**.

This is the dataset that should be used for the **Milestone 1 EDA**.

---

# 8. What Should You Do If You Want to Try It Yourself?

There are two simple choices.

## Option A — You only want to check the final data

You **do not need to run everything**.

Just load the **three final cleaned datasets**:

* `finmark_customer_demographics_cleaned_final.csv`
* `finmark_customer_transactions_cleaned_final.csv`
* `finmark_social_media_interactions_cleaned_final.csv`

Then you can run the cells that analyze the final datasets and create the graphs.

**This is the easiest option if you just want to work on the Milestone 1 EDA.**

---

## Option B — You want to understand and compare the whole cleaning process

If you want to see **what changed from beginning to end**, you need to load/run **all three versions**:

### Raw

Original datasets

↓

### Jeremiah's cleaned

First cleaning

↓

### Angel's final cleaned

Final cleaning

This lets you compare:

* What was wrong in the raw data?
* What did Jeremiah change?
* What did Angel change afterward?
* Why were some values changed to `Unknown`?
* Why were numerical values handled differently?
* What does the final dataset look like?

**If you want to understand the complete process, run all the datasets.**

---

# 9. What Should We Use for the Milestone 1 Report?

For the report, use the **final cleaned datasets** for the actual EDA.

Use the **raw datasets** when you need to explain the original problems.

Use **Jeremiah's cleaned datasets** when you want to explain the first cleaning stage or compare the team's preprocessing work.

### Easy rule:

> **Raw = What was wrong?**

> **Jeremiah's version = What was first cleaned?**

> **Angel's final version = What we use now for EDA?**

---

# 10. Final Dataset Results

After Angel's final cleaning and verification:

| Dataset                   |  Rows | Columns | Duplicate Rows | Missing Values |
| ------------------------- | ----: | ------: | -------------: | -------------: |
| Customer Demographics     | 3,023 |       6 |              0 |              0 |
| Customer Transactions     | 3,015 |       6 |              0 |              0 |
| Social Media Interactions | 3,020 |       6 |              0 |              0 |

The final datasets have:

* **0 duplicate rows**
* **0 actual missing (`NaN`) values**

Some `Unknown` labels are still present, and that is **intentional** for categorical information that we could not determine.

---

## ⭐ One thing to remember

> **Jeremiah did the first cleaning by removing duplicates and changing blanks to `Unknown`. Angel reviewed his work and kept `Unknown` for categories, but handled missing or invalid numbers differently by using `NaN` temporarily so Python could recognize them as numerical data. The final numbers were then properly handled.**
>
> **If you only want to check the final results, run the three FINAL datasets. If you want to understand and compare the whole cleaning process, run the Raw, Jeremiah's Cleaned, and Angel's Final datasets.**
