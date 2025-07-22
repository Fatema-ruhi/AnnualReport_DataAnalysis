# AnnualReport_DataAnalysis
“This project showcases my data analysis of the Missouri Office of Equal Opportunity FY23 Annual Report. I extracted, cleaned, and analyzed quantitative data from data warehouses using SQL, created summary tables and visuals using Tableau, and Excel, to provide insights on workforce demographics and diversity metrics.”

## 📊 Data Extraction and Analysis Process

### 🔹 Data Extraction

I extracted raw data directly from internal **data warehouses** using **SQL**. This involved writing complex queries with **JOINs**, **window functions (ROW\_NUMBER)**, **partitioning**, and **filters** to retrieve workforce and business certification data.

➡️ **Example SQL Query**:
*A sample query is provided here: (https://github.com/Fatema-ruhi/AnnualReport_DataAnalysis/blob/main/Sample%20SQL%20query).

### 🔹 Data Cleaning and Processing

* After extraction, I cleaned and pre-processed the data using Tableau Prep and Excel.
* Tasks included:

  * Removing duplicates and irrelevant records.
  * Filtering by certification status and date ranges.
  * Handling missing values in county and region mappings.
  * Formatting data for visualization-ready use.

### 🔹 Dashboarding and Visualization

* Built **interactive dashboards** in **Tableau Desktop** to visualize: (A sample of a Tableau Dashoboard: https://github.com/Fatema-ruhi/AnnualReport_DataAnalysis/blob/main/Dashboard%201%20overall.png).

  * Certification distribution by county, region, and business sector.
  * Trends in workforce diversity and business status.
  * Year-over-year changes and breakdowns by business classification codes.

* Created **summary tables and charts** aligned with reporting standards from the [FY23 OEO Annual Report](https://oeo.mo.gov/wp-content/uploads/2024/05/fy23-annual-report-final.pdf).

✅ **Result**: A fully automated pipeline starting from SQL-based raw data extraction, through data cleaning and transformation, to end-to-end reporting with **Tableau dashboards** and **Excel summaries**.

### 📊 **Summary of the Dashboard:**

This dashboard gives an overview of **supplier diversity across different regions in Missouri**. It shows information about **where businesses are located**, **what types of certifications they have**, **how they applied**, and **how the number of certified businesses has changed over time**.

### ✅ **Main Insights:**

**Regional Breakdown**:

  * Most certified businesses are in **St. Louis** and **Kansas City**.
  * Some regions, like **Northeast** and **Northwest Missouri**, have fewer certified businesses.
  * A good number of vendors are also from **outside Missouri**.

**Types of Certification**:

  * Many businesses are certified as **minority-owned (MBE)** or **women-owned (WBE)**.
  * Some have both certifications (**MBE/WBE**).

**Application Methods**:

  * Most businesses use the **standard application process**, while others use **faster in-state** or **out-of-state options**.

**Trends Over Time**:

  * The number of certified businesses has **gone up and down over the years**.
  * There were **big increases around 2015 and 2022**, but a **drop in 2024**.

**County and City Details**:

  * **Jackson County, St. Louis, and Franklin County** have the **highest number of businesses**.
  * Some counties have **very few certified businesses**.

**Types of Businesses**:

  * Businesses come from **many different industries**, especially **construction, healthcare, professional services, and IT**.

#### 4. **Write a Detailed README**

* Explain:

  * Your role in the analysis.
  * Tools and techniques used (e.g., Python libraries like `pandas`, `tabula-py` for PDF extraction, Excel, R, Tableau).
  * What parts of the report you analyzed and why.
  * Key findings or outcomes.
  * How this project demonstrates your data science skills.

#### 6. **Use GitHub Pages or Notebooks Viewer for Presentation**

* GitHub renders Jupyter notebooks and Markdown files beautifully so recruiters can view your analysis directly in the browser.
* Optionally, set up GitHub Pages for a simple project website with your summary.

### Example README Outline:

```markdown
# Missouri OEO FY23 Annual Report Data Analysis

This repository contains my data analysis work on the quantitative parts of the Missouri Office of Equal Opportunity FY23 Annual Report.

## Project Overview
- Extracted and cleaned numerical data from the official PDF report.
- Created summary tables and visualizations highlighting workforce demographics, budget, and program outcomes.
- Tools used: Python (pandas, tabula-py), Excel, Tableau.

## Source Document
[OEO FY23 Annual Report (PDF)](https://oeo.mo.gov/wp-content/uploads/2024/05/fy23-annual-report-final.pdf)

## Key Deliverables
- Data extraction scripts/notebooks
- Cleaned datasets (CSV)
- Summary tables
- Visualizations with insights

## Skills Demonstrated
- Data extraction from complex documents
- Data cleaning and preparation
- Quantitative analysis and reporting
- Data visualization
```

---

If you want, I can help you draft the actual README or a sample notebook outline for this project! Would that be helpful?
