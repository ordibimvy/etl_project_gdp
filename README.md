# 🌍 ETL Pipeline — Countries by GDP (Nominal)

## Overview
This project was developed by **Ordi Bimvy**, a Data Engineering student at Thomas College, as part of a practical ETL (Extract, Transform, Load) exercise.  
The goal was to build a complete ETL pipeline that scrapes real-world GDP data, transforms it into a structured format, and loads it into both a CSV file and a database table.

---

## 🧩 ETL Breakdown

### 1. Extract
- Source: [Wikipedia – List of countries by GDP (nominal)](https://en.wikipedia.org/wiki/List_of_countries_by_GDP_%28nominal%29)
- Tooling: `requests` + `BeautifulSoup`
- Logic:
  - Parse the webpage HTML.
  - Identify the correct table (`index 2` from `<tbody>` list).
  - Extract rows that contain valid data (non-empty, with hyperlink, and GDP not `'—'`).
  - Store extracted values into a pandas DataFrame.

### 2. Transform
- Clean GDP text data by removing commas and converting from string → float.
- Convert GDP from **USD Millions → USD Billions**.
- Round all values to **2 decimal places** using NumPy.
- Rename column `GDP_USD_millions` → `GDP_USD_billions`.

### 3. Load
- Save the cleaned dataset to a **CSV file** (`Countries_by_GDP.csv`).
- (Optional) Load the same data into a SQLite database (`World_Economies.db`) for analysis.

---

## 🧠 Skills & Tools Demonstrated
- **Python Libraries:** `pandas`, `numpy`, `requests`, `BeautifulSoup`, `sqlite3`, `datetime`
- **ETL Concepts:** data extraction, transformation, cleaning, and loading
- **Data Engineering Practices:** logging, incremental pipeline design, reproducible code
- **Analytical Thinking:** identifying valid data patterns and structuring unstructured data

---

# Run the script
python etl_project_gdp.py
