# AnnualReport_DataAnalysis
“This project showcases my data analysis of the Missouri Office of Equal Opportunity FY23 Annual Report. I extracted, cleaned, and analyzed quantitative data from data warehouses using SQL, created summary tables and visuals using Tableau, and Excel, to provide insights on workforce demographics and diversity metrics.”

* Include:

Here’s a clean and professional draft you can use in your **GitHub README** to clearly explain your steps. You can simply copy-paste and adjust as needed:

---

## 📊 Data Extraction and Analysis Process

### 🔹 Data Extraction

I extracted raw data directly from internal **data warehouses** using **SQL**. This involved writing complex queries with **JOINs**, **window functions (ROW\_NUMBER)**, **partitioning**, and **filters** to retrieve workforce and business certification data.
➡️ **Example SQL Query**:
*A sample query is provided in the `sql_queries/` folder (or see below).*

```sql
/* Put all the different business codes in this list.*/


Select distinct
[CertificationID],
[UNSPSCCode],
[Title],
[Fam_Ranking],
--[Ranking],
[CertificationStatusID],
[ApplicationProcessDescription],
[CertificationDescription],
[CertificationStatusDescription],
[BusinessName],
[BusinessCity],
[BusinessCounty],
[BusinessState],
[CountyName],
[RegionName],
[CertificationDate],
[UpdatedDate]

From(
	Select
	[CertificationID],
	[UNSPSCCode],
	[Title],
	[Fam_Ranking],
	--[Ranking] = Max([Fam_Ranking]) Over (Partition by [CertificationID], Left([UNSPSCCode], 2) order by [UNSPSCCode]),
	[CertificationStatusID],
	[ApplicationProcessDescription],
	[CertificationDescription],
	[CertificationStatusDescription],
	[BusinessName],
	[BusinessCity],
	[BusinessCounty],
	[BusinessState],
	[CountyName],
	[RegionName],
	[CertificationDate],
	[UpdatedDate]
	From(
			Select
				UCU.[CertificationID], UC.[Title], UC.[UNSPSCCode],
				[Fam_Ranking] = ROW_NUMBER() OVER (PARTITION BY C.[CertificationID], left([UNSPSCCode],2) ORDER BY UC.[UNSPSCCode]),
				C.[CertificationStatusID], ap.[ApplicationProcessDescription], cet.[CertificationDescription], cst.[CertificationStatusDescription], C.[BusinessName], C.[BusinessCity], C.[BusinessCounty], C.[BusinessState], ct.[CountyName], r.[RegionName], C.[CertificationDate], C.[UpdatedDate]

			FROM [OA_MWBCert].[dbo].[Certification] C
			JOIN [OA_MWBCert].[dbo].[CertificationUNSPSCCode] UCU ON C.CertificationID = UCU.CertificationID
			join [OA_MWBCert].[dbo].[Application] a on a.[CertificationID] = C.[CertificationID]
			JOIN [OA_MWBCert].[dbo].[UNSPSCCode] UC ON UC.UNSPSCCodeID = UCU.UNSPSCCodeID
			join [OA_MWBCert].[dbo].[CertificationType] cet on cet.[CertificationTypeID] = C.[CertificationTypeID]
			Full join [OA_MWBCert].[dbo].[County] ct on ct.[CountyID] = C.[BusinessCounty]
			Full join [OA_MWBCert].[dbo].[Region] r on ct.[regionID] = r.[RegionID]
			join [OA_MWBCert].[dbo].[CertificationStatus] cst on cst.[CertificationStatusID] = C.[CertificationStatusID]
			join [OA_MWBCert].[dbo].[ApplicationProcess] ap on ap.[ApplicationProcessID] = a.[ApplicationProcessID]
		  
			Where C.[CertificationStatusID] = '2' --and left([UNSPSCCode],2) = '10'      --If you want to see only one segment, change the segment value accordingly and uncomment 'left([UNSPSCCode],2)'.
	) A
) X
Where [Fam_Ranking] = '1' 
Order By [CertificationID]
```

### 🔹 Data Cleaning and Processing

* After extraction, I cleaned and pre-processed the data using Tableau Prep and Excel.
* Tasks included:

  * Removing duplicates and irrelevant records.
  * Filtering by certification status and date ranges.
  * Handling missing values in county and region mappings.
  * Formatting data for visualization-ready use.

### 🔹 Dashboarding and Visualization

* Built **interactive dashboards** in **Tableau Desktop** to visualize:

  * Certification distribution by county, region, and business sector.
  * Trends in workforce diversity and business status.
  * Year-over-year changes and breakdowns by business classification codes.

* Created **summary tables and charts** aligned with reporting standards from the [FY23 OEO Annual Report](https://oeo.mo.gov/wp-content/uploads/2024/05/fy23-annual-report-final.pdf).

---

✅ **Result**: A fully automated pipeline starting from SQL-based raw data extraction, through data cleaning and transformation, to end-to-end reporting with **Tableau dashboards** and **Excel summaries**.

---

Let me know if you want me to **generate this full README for you** with folder structure suggestions!

  * Tables and visualizations: Include the key tables you created or graphs that summarize findings.
  * Summary and insights: Brief text blocks explaining what the data shows.

#### 3. **Add the Original Annual Report Link**

* Put the link in the README file and mention that this is the source document you analyzed.

#### 4. **Write a Detailed README**

* Explain:

  * Your role in the analysis.
  * Tools and techniques used (e.g., Python libraries like `pandas`, `tabula-py` for PDF extraction, Excel, R, Tableau).
  * What parts of the report you analyzed and why.
  * Key findings or outcomes.
  * How this project demonstrates your data science skills.

#### 5. **Optional: Include Sample Data or Processed Tables**

* If you can legally share, upload CSV files with cleaned quantitative data or sample tables.

#### 6. **Use GitHub Pages or Notebooks Viewer for Presentation**

* GitHub renders Jupyter notebooks and Markdown files beautifully so recruiters can view your analysis directly in the browser.
* Optionally, set up GitHub Pages for a simple project website with your summary.

---

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
