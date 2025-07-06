# 🐶 WeRateDogs Twitter Data Wrangling Report

This report summarizes the key steps and observations made during the data wrangling process of the WeRateDogs Twitter project. The wrangling process consisted of **gathering**, **assessing**, and **cleaning** data to make it suitable for analysis and visualization.

---

## 1. 📥 Gathering Data

Three different data sources were used:

1. **`twitter_archive.csv`**  
   - Provided as a CSV file from Udacity.

2. **`image_predictions.tsv`**  
   - Downloaded programmatically from the Udacity-provided URL.

3. **`tweet_json.txt`**  
   - Collected using the Twitter API and saved in text format as JSON data.

---

## 2. 🔍 Assessing the Data

The datasets were assessed both **visually** and **programmatically** using functions such as `.head()`, `.info()`, `.describe()`, `.duplicated()`, and `.value_counts()`.

### ✨ Quality Issues Identified

| Dataset              | Issue Description |
|----------------------|------------------|
| `twitter_archive`    | Incorrect data types (e.g., `tweet_id`, `timestamp`) |
| `image_predictions`  | `tweet_id` stored as incorrect type |
| `tweet_json`         | Incorrect `tweet_id` type |
| All datasets         | Presence of missing/deleted tweets |
| `twitter_archive`    | Ambiguous or missing dog names |
| `twitter_archive`    | Irrelevant columns (e.g., retweet/reply-related data) |
| `twitter_archive`    | Inaccurate values in `rating_numerator` (e.g., 1776) indicating outliers |
| Cleaned dataset      | Some classification fields (`p1`, `p2`, `p3`) and rating fields had incorrect data types |

### 🧹 Tidiness Issues Identified

- The three datasets should be **merged into a single master dataset** using `tweet_id`.
- The dog stage columns (`doggo`, `floofer`, `pupper`, `puppo`) should be **combined into a single categorical column**.

---

## 3. 🧼 Cleaning the Data

Cleaning was the most challenging part of the wrangling process. It involved:

- **Fixing data types**: Casting `tweet_id` to string, converting timestamps to datetime.
- **Removing duplicates and irrelevant columns**: Dropping unnecessary retweet and reply-related fields.
- **Handling missing and ambiguous values**: Replacing dog names such as `"None"` or `"a"` with `NaN`.
- **Correcting outliers**: Identifying and filtering out unrealistic rating values.
- **Tidying structure**: Merging the datasets and reshaping the dog stage columns into one.

Despite being new to data wrangling, I made a strong attempt to resolve all quality and tidiness issues for a clean and analysis-ready dataset.

---

## 🔁 Reassessment

After cleaning, the dataset was reassessed to verify that:
- Data types were appropriate.
- Duplicates were removed.
- Merged structure was consistent.
- No remaining obvious anomalies or structural issues existed.

---

## ✅ Conclusion

The dataset has been successfully wrangled and is now clean and tidy. It is well-suited for exploratory analysis and visualization. The wrangling process, while demanding, was a valuable learning experience in mastering real-world data preparation.

---

**Prepared by**: Waqar Ahmed  
📧 *waqar.nu@gmail.com*  
📁 *Project Repository*: [https://github.com/waqar-ahmed91/Data-Wrangling-and-Analysis-of-WeRateDogs-Twitter-Account]
