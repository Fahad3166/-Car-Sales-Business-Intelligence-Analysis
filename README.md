# 🚗 Car Sales Business Intelligence Analysis
### University of Vienna – Business Intelligence 1 | Assignment 1 | Summer Semester 2024
**Fahad Ali
---
## 📌 Project Overview

This project explores the **Retail (Car Sales) domain** using Business Intelligence techniques. We integrated two public datasets to build a data pipeline, star schema, and interactive Tableau dashboard to answer key analytical questions about car sales, pricing, fuel efficiency, and resale values.

---

## 🔍 Analytical Questions

1. How do car sales vary across different brands or models?
2. How does fuel efficiency relate among different car models?
3. Which features of a car have more impact on car sales?
4. How does engine power relate to car price and mileage?
5. Which vehicle types are associated with higher resale values?

---

## 📂 Datasets

| Dataset | Source | Size |
|---|---|---|
| German Car Insights | [Kaggle](https://www.kaggle.com/datasets/yaminh/german-car-insights) | ~100,000 entries, 15 columns |
| Car Sales Data | [Kaggle](https://www.kaggle.com/datasets/gagandeep16/car-sales) | ~153 entries, 16 columns |

---

## 🗂️ Project Structure

```
├── data/
│   ├── raw/                  # Original source CSV files
│   └── processed/            # Transformed data (Tableau-ready)
├── notebooks/
│   └── data_pipeline.ipynb   # Full ETL pipeline (Jupyter Notebook)
├── tableau/
│   └── dashboard.twb         # Tableau workbook
├── report/
│   └── Report_Assignment_1_BI.pdf
└── README.md
```

---

## ⚙️ Data Pipeline

The Jupyter Notebook (`notebooks/data_pipeline.ipynb`) covers the full ETL process:

### 🔄 Data Transformation
- Downloaded datasets as CSV
- Identified and assigned Primary Keys
- Created relationships using Foreign Keys
- Removed irrelevant attributes (e.g., `Unnamed: 0`, `Latest Launch`)

### 🔗 Data Integration
- Merged datasets using an **inner join** on Manufacturer/Brand
- Standardized model names to match across datasets
- Built dimension tables: `Dimension_Car`, `Dimension_Date`, `Dimension_Fuel`

### 🧹 Data Cleaning
- Filled missing numerical values using **median imputation**
- Filled missing `color` values using **mode**
- Converted `power_kw` / `power_ps` and `price_in_euro` from string to numeric

---

## 🌟 Star Schema

The BI data model follows a **star schema** with:

- **Fact Table:** `Car_Sales_Fact` (Car_Sales_ID, Car_ID, Resale_ID, Date_ID, Fuel_ID, Mileage_ID)
- **Dimensions:** `Dimension_Car`, `Dimension_Date`, `Dimension_Fuel`, `Dimension_Mileage`, `Dimension_Yearly_Resale_Value`

---

## 📊 Key Insights

- **Ford F-Series** had the highest sales volume among all models
- Higher-priced cars generally show lower fuel efficiency
- **Passenger vehicles** tend to have higher resale values than standard cars
- Engine power correlates positively with both price and mileage

---

## 🛠️ How to Run

1. Clone this repository
2. Download the raw datasets from the Kaggle links above and place them in `data/raw/`
3. Open and run `notebooks/data_pipeline.ipynb` top to bottom
4. Load the generated CSV files from `data/processed/` into Tableau
5. Open `tableau/dashboard.twb` to view the dashboard

### Requirements
```
Python 3.x
pandas
numpy
jupyter
```
Install dependencies:
```bash
pip install pandas numpy jupyter
```

---

## 👥 Work Distribution

| Task | Contributor |
|---|---|
| Data Research | Both |
| Analytical Questions (Q1, Q2) | Wishal Fatima |
| Analytical Questions (Q3, Q4, Q5) | Fahad Ali |
| ERD Model | Fahad Ali |
| Star Schema | Both |
| Jupyter Notebook | Both |
| Tableau Dashboard | Both (own questions) |
| Report | Both |

---

## 🎓 Course Info

- **Course:** 2024S 052411-1 Business Intelligence 1
- **Institution:** University of Vienna
- **Semester:** Summer 2024

