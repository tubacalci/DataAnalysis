# 🍽️ Zomato Data Cleaning & Preparation

Welcome to the **Zomato Data Cleaning** project!  
This repository showcases how to clean and prepare a real-world restaurant dataset using **Python**, **Pandas**, and **Jupyter Notebook**.  
It follows a step-by-step data wrangling pipeline to make the dataset analysis-ready.

---

## 📊 Dataset

⚠️ **Note:** The original dataset is **not included** due to size constraints.  
You can download it manually from Kaggle:

🔗 [Zomato Restaurants Dataset – Kaggle](https://www.kaggle.com/datasets/rishikeshkonapure/zomato)

---

## 📁 Project Structure

| File | Description |
|------|-------------|
| `DataCleaning-Zomato.ipynb` | Main Jupyter Notebook with the complete cleaning process |
| `cleaned_zomato_data.xls` | Final cleaned dataset exported to CSV format |

---

## 🧼 Data Cleaning Workflow

The cleaning process consists of the following steps:

### 🗑️ 1. Deleting Redundant Columns
- Removed columns such as `url`, `address`, and others not relevant for analysis.

### 📝 2. Renaming the Columns
- Standardized all column names by capitalizing the first letter of each (e.g., rate → Rate, location → Location)

### 📛 3. Dropping Duplicates
- Removed fully duplicated rows.

### 🚫 4. Removing NaN Values
- Dropped rows with missing values in important columns (like `Rate`, `Location`, etc.).

### 🧹 5. Cleaning Individual Columns
- Rate Column:
  Removed extra spaces.
  Replaced values like "4.1/5" with more readable "4.1 out of 5".

### 🔁 6. Additional Transformations
- Converted categorical flags (`Online_order`, `Book_table`) to binary values.

### 💾 7. Export Final Cleaned Dataset
- Exported cleaned dataset to `.csv` format using `index=False` to avoid `Unnamed: 0` column issues.

---
