# World Development & Geopolitical Analytics (DEPI Mini-Project 3)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)](https://pandas.pydata.org/)
[![Tableau](https://img.shields.io/badge/Tableau-Dashboard%20%26%20Story-E97627.svg)](https://www.tableau.com/)

An end-to-end data analytics project exploring global macroeconomic performance, international trade, demographic dynamics, and energy infrastructure. Created as part of the **Digital Egypt Pioneers Initiative (DEPI) - Data Analytics Track (Round 5)**.

---

## 📌 Project Overview

This project provides an interactive and structured analysis of global country indicators across **263 nations and territories** and **45 variables**. Using Python for data preprocessing and Tableau for dynamic visualization, the analysis explores key global relationships, such as economic productivity vs. life expectancy, trade imbalances, energy resource distribution, and transportation networks.

### 🔗 Quick Links
* **GitHub Repository:** [Faragello005/Mini-Project-Tableau](https://github.com/Faragello005/Mini-Project-Tableau)
* **Workbook File:** `Cleaned_Imputed_Country_Data.twb`

---

## 🛠️ Data Preprocessing & Cleaning (Python / Pandas)

The raw dataset (`Country Data Comparison.csv`) contained significant missingness, structural artifacts, and formatting issues. Data cleaning was performed using a Jupyter Notebook (`Data_Cleaning_.ipynb`).

```
Raw Data (264, 45) ➔ Header Standardizing ➔ Numeric Parsing ➔ Domain Imputation ➔ Clean Data (263, 45)
```

### Key Preprocessing Steps & Challenges:
1. **Parsing & Formatting:**
   * Handled semicolon-delimited input data (`sep=';'`).
   * Stripped metadata rows and white spaces from column headers.
   * Converted 43 non-string columns into clean numerical floats (`pd.to_numeric`).
   * Verified country uniqueness (0 duplicate records found).

2. **Handling High-Density Missing Values (The Core Challenge):**
   * *Challenge:* Several energy and infrastructure columns had under 25% non-null values (e.g., Oil Exports had only 58 reported values out of 263).
   * *Solution Strategy:*
     * **Zero Infill (`0`):** Applied to structural non-occurrences (e.g., landlocked or non-producing countries missing oil/gas reserves, production, or railway networks).
     * **Median Imputation:** Applied median values across general demographic and economic features to preserve underlying distributions without distorting extreme outliers.

---

## 📊 Tableau Workbook Architecture

The Tableau workbook includes **7 visualization types**, **3 interactive dashboards**, **16 cross-filtering action filters**, dynamic parameters, and a **4-frame Tableau Story**.

### 📱 Dashboards

| Dashboard | Visual Components | Focus Area |
| :--- | :--- | :--- |
| **1. Economic Performance & Trade** | Choropleth Map, Top 10 Ranking Bar Chart, Trade Balance Matrix | GDP, GDP per capita, total exports/imports, trade surpluses, and structural trade deficits. |
| **2. Demographics & Global Health** | Wealth vs. Health Scatter Plot (Linear Regression), Infant Mortality vs. Fertility Dual-Axis Chart | Diminishing returns of GDP per capita on life expectancy and fertility-mortality transitions. |
| **3. Energy Resources & Infrastructure** | Packed Bubble Chart, Gas Production vs. Consumption Bar, Highways vs. Railways Bullet Chart | Global oil/gas production concentration, energy import dependencies, and freight infrastructure. |

### 💡 Dynamic Parameters & Calculated Fields
* **`[Metric Selector]` (Parameter):** Enables users to dynamically toggle map and ranking views between *GDP per capita*, *Population*, *Exports*, and *Electricity Consumption*.
* **`[Trade Balance]`:** Calculated field determining net trade status (`[Exports] - [Imports]`).
* **`[Trade Status]`:** Categorical segmentation (`Trade Surplus` vs. `Trade Deficit`).
* **`[Net Birth Rate]`:** Demographic growth indicator (`[Birth rate] - [Death rate]`).
* **`[Net Oil Exporter]`:** Energy balance metric (`[Oil production] - [Oil consumption]`).

---

## 📖 Storyboard Structure (`Story 1`)

The workbook wraps up key findings into a 4-frame executive narrative:
1. **The Global Economic Divide:** Focuses on wealth concentration and global trade imbalances.
2. **Does Money Buy Life Expectancy?:** Demonstrates the logarithmic return of GDP per capita on life expectancy.
3. **Energy & Infrastructure:** Examines energy production disconnects and highway vs. rail logistics.
4. **Key Findings & Strategic Summary:** Summarizes actionable policy takeaways across healthcare, energy transition, and infrastructure modernization.

---

## 📁 Repository Structure

```
├── Data_Cleaning_.ipynb             # Python cleaning & imputation notebook
├── Cleaned_Imputed_Country_Data.csv # Cleaned dataset ready for Tableau
├── Cleaned_Imputed_Country_Data.twb # Tableau Workbook file
└── README.md                        # Project documentation
```

---

## 🚀 How to Run the Project

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/Faragello005/Mini-Project-Tableau.git
   cd Mini-Project-Tableau
   ```
2. **Run Data Cleaning (Optional):**
   Ensure Python 3.x, `pandas`, and `numpy` are installed, then run `Data_Cleaning_.ipynb`.
3. **Open Tableau Workbook:**
   Open `Cleaned_Imputed_Country_Data.twb` using Tableau Desktop or Tableau Public.
