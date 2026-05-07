Startup Fundraising Analysis (Crunchbase Dataset)

**Project:** 2  
**Difficulty:** Beginner  
**Tools:** SQLite, Juypter Notebook, Python,
**Focus:** Data Cleaning, Analysis, Using SQLite through a Python import, using pandas import.

Project Overview

This project explores startup investment data from the Crunchbase dataset using a combined **pandas + SQLite workflow**. The objective was to transform raw, unstructured data into a clean, queryable format and derive insights into **fundraising trends, sector performance, and funding patterns**.

The project follows a full data pipeline:

* Data ingestion from CSV
* Data cleaning and transformation
* Storage in a relational database (SQLite)
* Analytical querying using SQL
* Interpretation of business insights

---

Tools & Technologies

* **Python**
* **Pandas**
* **SQLite**
* **Jupyter Notebook**

---

Dataset

* Source: Crunchbase Startup Investments dataset
* Records:

  * Raw dataset: **~54,294 rows**
  * Cleaned dataset: **40,907 rows**

---

Data Processing Workflow

### 1. Data Exploration

* Inspected dataset structure, data types, and missing values
* Identified key issues:

  * Funding amounts stored as text
  * Date fields in string format
  * Inconsistent column naming
  * Missing and placeholder values

---

2. Data Loading (SQLite Integration)

* Loaded CSV into SQLite using **chunk-based processing**
* Prevented duplication by using:

  * `replace` for the first chunk
  * `append` for subsequent chunks
* Created a structured relational table for querying

---

3. Data Cleaning & Transformation

Key transformations included:

* Renaming inconsistent columns (e.g. `_funding_total_usd_` → `funding_total_usd`)
* Converting funding values to numeric format
* Handling invalid placeholders (e.g. '-', empty values)
* Converting date columns to datetime
* Standardising `founded_year` to integer
* Removing records with missing or invalid funding values

Result:

* ~25% of records removed due to poor data quality

---

Key Analysis & Insights

1. Funding Trends Over Time

* Startup activity increased significantly from the early 2000s
* Peak funding observed around **2010–2012**
* Average funding per company decreased over time, indicating broader distribution of capital

---

2. Most Successful Startup Verticals

* **Biotechnology** received the highest total funding
* **Mobile** had the highest average funding per company
* **Software** had many companies but lower average funding, indicating a competitive market

---

3. Funding Round Distribution

* Majority of startups received only **1–2 funding rounds**
* Sharp drop-off in later rounds
* Indicates high attrition beyond early-stage funding

---

4. Funding Type Analysis

* **Venture capital** dominated total funding
* **Private equity** and **debt financing** contributed significantly at later stages
* Early-stage funding (seed, angel) occurred frequently but with lower capital amounts

---

5. Investment Concentration

* Funding is highly concentrated among a small number of companies
* Top firms received disproportionately large amounts of capital
* Indicates unequal distribution of investment across the startup ecosystem

---

Challenges & Limitations

1. Data Quality Issues

* Missing and inconsistent values required significant cleaning
* Funding column stored as text with symbols and placeholders
* Category fields were not fully normalised

2. Database Duplication Issue

* Initial data loading caused duplicate records due to repeated `append` operations
* Resolved by:

  * Rebuilding the database from scratch
  * Implementing controlled chunk loading (`replace` + `append` logic)

3. Lack of Investor-Level Data

* Dataset does not include investor names
* Prevented direct analysis of investor activity
* Adapted approach by analysing:

  * Funding types
  * Company-level investment patterns


4. Outliers in Funding Data

* Extremely large funding values skewed averages
* Required careful interpretation of results



Key Skills Demonstrated

* Data cleaning and preprocessing
* SQL querying and aggregation
* Database management (SQLite)
* Handling large datasets with chunking
* Data validation and debugging
* Translating data into business insights



Conclusion

This project demonstrates an end-to-end data analysis workflow, from raw data ingestion to actionable insights. It highlights real-world challenges such as data quality issues, duplication errors, and dataset limitations, while showcasing the ability to adapt analysis techniques accordingly.

Future Improvements

* Normalise category fields for more accurate sector analysis
* Incorporate additional datasets with investor-level detail
* Apply visualisation tools (e.g. Power BI, Tableau) for dashboard reporting

