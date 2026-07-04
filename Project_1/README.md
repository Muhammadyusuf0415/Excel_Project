# Excel Salary Dashboard

<img src="../images_and_gifs/1_Salary_Dashboard_Final_Dashboard.gif" alt="final dashboard" width="500">

## Introduction

I analyzed **2,400+ data science job postings from 2023** to uncover salary trends across roles, regions, and employment types. This interactive dashboard lets you filter by job title and location to benchmark your market rate—discovering insights like the **45% salary gap between junior analysts and senior engineers**.

### 📊 Dashboard File

Open the interactive dashboard: [Job_Market_Analysis.xlsx](Job_Market_Analysis.xlsx)

### Excel Skills Used

- **📉 Charts** — Bar charts & geographic map charts
- **🧮 Formulas and Functions** — Array formulas, MEDIAN, FILTER
- **❎ Data Validation** — Dropdown filters for seamless interaction

### 📋 Data Jobs Dataset

Real-world data science job information from 2023, containing:

- **Job titles** (Analyst, Engineer, Scientist, etc.)
- **Annual salaries** (ranging across experience levels)
- **Locations** (global coverage across multiple countries)
- **Employment types** (Full-time, Contract, Part-time)

---

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="../images_and_gifs/1_Salary_Dashboard_Chart1.png" alt="bar chart" width="500">

**Key Insight:** Senior roles and Engineers command significantly higher median salaries (up to 45% more) compared to Analyst positions.

**Why this chart?** Horizontal bars allow quick visual ranking of salary levels by job title, making it easy to spot which roles pay best.

#### 🗺️ Country Median Salaries - Map Chart

<img src="../images_and_gifs/1_Salary_Dashboard_Country_Map.gif" alt="map chart" width="500">

**Key Insight:** Global salary disparities are stark—high-paying regions (USA, Canada) stand out visually against lower-paying markets.

**Why this chart?** Geographic visualization instantly reveals where salaries are strongest worldwide.

---

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

**What it does:** Returns the median salary filtered by job title, country, employment type, and excludes zero/blank values.

**Why it works:** The nested `IF()` statement creates a multi-criteria filter, and `MEDIAN()` handles the array operation, giving us accurate salary benchmarks for any combination of filters.

**Background Table Example:**

<img src="../images_and_gifs/1_Salary_Dashboard_Screenshot1.png" alt="btable" width="350">

**Dashboard in Action:**

<img src="../images_and_gifs/1_Salary_Dashboard_Job_Title.png" alt="implementation" width="350">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

**What it does:** Generates a unique list of job schedule types by filtering out entries with "and" or commas, and removes zero values.

**Why it works:** The `FILTER()` function cleans up the raw data, ensuring only valid, unique options appear in the dropdown.

**Background Table Example:**

<img src="../images_and_gifs/1_Salary_Dashboard_Screenshot2.png" alt="screenshot" width="350">

**Dashboard in Action:**

<img src="../images_and_gifs/1_Salary_Dashboard_Type.png" alt="implementation" width="350">

---

### ❎ Data Validation

#### 🔍 How to Use the Dashboard

The dashboard uses **dropdown filters** for three categories:

- **Job Title** — Select from Analyst, Engineer, Scientist, or other roles
- **Country** — Choose any country in the dataset
- **Type** — Filter by employment type (Full-time, Contract, Part-time)

Simply select your criteria, and the charts and salary table update instantly to show relevant insights.

<img src="../images_and_gifs/1_Salary_Dashboard_Data_Validation%20(1).gif" alt="data validation" width="350">

**Why data validation?** Restricting inputs to predefined options prevents errors and ensures consistent, reliable results.

---

## Key Learnings

- **Array formulas are powerful** — Using `MEDIAN()` + `IF()` proved more flexible than pivot tables for dynamic salary comparisons
- **Geographic data tells a story** — Map charts make salary disparities immediately obvious without requiring manual region parsing
- **User-friendly dashboards need constraints** — Data validation transforms a static analysis into an interactive tool

---

## Conclusion

This project demonstrates how Excel can transform raw job market data into actionable insights. By combining formulas, charts, and validation, I created a tool that lets job seekers quickly understand their market value. Whether you're negotiating salary or planning your career path, this dashboard provides the data-driven evidence you need.

**Next steps:** Download the file, experiment with different filters, and discover your ideal salary range based on role, location, and employment type.

---

## 📥 How to Get Started

1. Download **[Job_Market_Analysis.xlsx](Job_Market_Analysis.xlsx)**
2. Open in Microsoft Excel or compatible spreadsheet software
3. Use the dropdown filters to explore salary trends
4. Refer to the charts for visual insights

Have feedback or suggestions? Feel free to reach out!
