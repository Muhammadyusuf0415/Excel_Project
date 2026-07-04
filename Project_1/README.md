# Excel Salary Dashboard

<p align="center">
  <img src="../images_and_gifs/1_Salary_Dashboard_Final_Dashboard.gif" width="700">
</p>

## Overview

An interactive Excel dashboard built using **2,400+ data science job postings** to analyze salary trends across job titles, countries, and employment types.

### Dashboard Features

- Filter salaries by **Job Title**
- Analyze salaries by **Country**
- Compare **Employment Types**
- View **Median Salary**, **Job Count**, and **Top Job Platform**
- Interactive charts and map visualization

### Skills Demonstrated

- Excel Charts
- Map Charts
- Dynamic Array Formulas
- `MEDIAN()`
- `FILTER()`
- Data Validation
- Dashboard Design

### Dashboard File

📄 **[Job_Market_Analysis.xlsx](Job_Market_Analysis.xlsx)**

---

# Dashboard Preview

<img src="../images_and_gifs/1_Salary_Dashboard_Final_Dashboard.gif" width="700">

---

# Key Visuals

### Salary by Job Title

<img src="../images_and_gifs/1_Salary_Dashboard_Chart1.png" width="550">

Shows the median salary for each data-related role.

---

### Country Salary Map

<img src="../images_and_gifs/1_Salary_Dashboard_Country_Map.gif" width="550">

Highlights salary differences across countries.

---

# Key Formula

```excel
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

Calculates the dynamic median salary based on selected filters.

---

# Data Validation

<img src="../images_and_gifs/1_Salary_Dashboard_Data_Validation%20(1).gif" width="350">

Dropdown menus allow users to interactively filter the dashboard.

---

# Key Takeaways

- Built an interactive Excel dashboard from raw data
- Created dynamic calculations using array formulas
- Designed user-friendly filtering with Data Validation
- Visualized salary trends using charts and maps
