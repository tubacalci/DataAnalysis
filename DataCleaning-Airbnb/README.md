# 🧹 DataAnalysis

Welcome to the **DataAnalysis** repository!  
This project contains data exploration and cleaning workflows using **Python**, **Pandas**, and **Jupyter Notebook**.  
The focus is on real-world data quality issues and best practices in preparing datasets for analysis or machine learning.

---

## 📊 Dataset

Original dataset downloaded from Kaggle:  
🔗 [Airbnb Open Data – Kaggle](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata)

---

## 📁 Project Structure

### `DataCleaning-Airbnb/`

This folder contains a complete cleaning pipeline for an Airbnb dataset.

It includes:
- The original dataset
- Cleaned versions (in CSV and Excel formats)
- Jupyter Notebook demonstrating all steps

---

## 🧼 Data Cleaning Workflow Summary

All data cleaning operations are performed in the `DataCleaning-Airbnb.ipynb` notebook. Here's what has been done:

### ✔️ 1. Dropping Duplicates and Missing Values
- Removed completely duplicated rows
- Dropped rows with missing critical information (e.g., `price`, `service fee`)

### ✔️ 2. Column-Specific Cleaning
- Converted `last review` column to proper `datetime` format
- Standardized text fields (`host_identity_verified` converted to uppercase, then encoded as 0/1)
- Cleaned `price` and `service fee` columns by removing dollar signs and converting to `float`
- Encoded `cancellation_policy` as ordinal (flexible → moderate → strict)
- Converted `instant_bookable` from `'t'/'f'` to `1/0`

### ✔️ 3. Feature Engineering
- Created a `Building Age` column from the `Construction year`
- Categorized `Building Age` into bins: `new`, `moderate`, and `old`

### ✔️ 4. Exporting Final Datasets
- Exported cleaned data to:
  - `.csv` format (with and without index)
  - `.xlsx` format (with and without index)

---

## 📄 Files in `DataCleaning-Airbnb/`

| File Name | Description |
|-----------|-------------|
| `DataCleaning-Airbnb.ipynb` | Main notebook showing all cleaning steps |
| `Airbnb_Open_Data.xls` | Raw Airbnb dataset |
| `cleaned_data.xls` | Cleaned dataset saved with Pandas index |
| `cleaned_data_without_index.xls` | Cleaned dataset saved **without index**, to avoid `"Unnamed: 0"` issue |
| `excel_cleaned_data.xlsx` | Cleaned dataset exported to Excel (with index) |
| `excel_cleaned_data_index_false.xlsx` | Excel version **without index**, avoids column misalignment on load |

### ℹ️ Why separate files without index?
When saving a DataFrame with `to_csv()` or `to_excel()` **without `index=False`**, Pandas adds the index column.  
When reloading the file later, this causes an unwanted `"Unnamed: 0"` column.

To prevent this issue:
- `cleaned_data_without_index.xls`
- `excel_cleaned_data_index_false.xlsx`

were created using `index=False`.

---
