![Project overview screenshot](../images2/Capture.PNG)
![Power Query example](../images2/Capture2.PNG)
![Power Pivot / Data Model](../images2/Capture3.PNG)
![Final charts](../images2/Capture4.PNG)

# Project 2 — Data Science Job Market Analysis

## Overview
This project analyzes the 2023 data science job market to identify which skills are most requested and how skills relate to salary. Using Excel (Power Query, Power Pivot, DAX, PivotTables and PivotCharts), I explored job titles, salaries, locations, and skills from a curated dataset of real job postings.

Key questions:
- Do more skills get you better pay?
- What are the salaries for data jobs in different regions?
- What are the top skills of data professionals?
- What is the pay associated with the top 10 skills?

## Files included
- data_salary_all.xlsx — original dataset (Excel file; not viewable here)
- Project_2/README.md — this file
- images (folder: ../images2/) — screenshots and charts used in this README:
  - 2_Project_Analysis_Screenshot1.png
  - 2_Project_Analysis_Screenshot2.png
  - 2_Project_Analysis_Screenshot3.png
  - 2_Project_Analysis_Screenshot4.png
  - 2_Project_Analysis_Chart1.png
  - 2_Project_Analysis_Chart2.png
  - 2_Project_Analysis_Chart3.png
  - 2_Project_Analysis_Chart4.png

> Note: I could not open the Excel file directly; this README is prepared based on your descriptions and the screenshots you provided.

---

## Tools & Excel skills used
- Power Query (ETL) — extract, clean, and transform raw data
- Power Pivot & Data Model — relate tables and create measures
- DAX — create measures and calculate medians
- PivotTables & PivotCharts — summarization and visualization
- Advanced chart customization (combo charts, secondary axis, markers)

## Dataset
The dataset contains job postings from 2023 with fields including:
- job_id, job_title, job_title_short
- salary_year_avg (annual salary)
- job_country, job_region
- skills (one-to-many: job → skills)

## Analysis steps (summary)

### 1) Extract & Transform (Power Query)
- Loaded data_salary_all.xlsx into Power Query.
- Created two queries:
  - `data_jobs_all` — main job table (one row per job).
  - `data_job_skills` — mapping of job_id → skill (one row per skill per job).
- Cleaned text, trimmed whitespace, removed unnecessary columns, and normalized skill names.
![Power Query transform screenshot](../images2/2_Project_Analysis_Screenshot1.png)

### 2) Build Data Model (Power Pivot)
- Loaded both queries into the Data Model.
- Created a relationship on `job_id` between `data_jobs_all` and `data_job_skills`.
- Added DAX measures (median salary, skill likelihood, etc.).
![Power Pivot / Data Model screenshot](../images2/2_Project_Analysis_Screenshot2.png)

Example DAX measures used:
```dax
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])

Median Salary (US) :=
CALCULATE(
  MEDIAN(data_jobs_all[salary_year_avg]),
  data_jobs_all[job_country] = "United States"
)
```

### 3) PivotTables & PivotCharts (Analysis & Visualization)
- Created PivotTables from the Data Model to compute:
  - Median salary by job title and region.
  - Frequency / likelihood (%) of each skill.
  - Median salary for jobs requiring each skill.
- Visualized results using combo charts (clustered column for median salary + line for skill likelihood).
![PivotTable and Chart example](../images2/2_Project_Analysis_Screenshot3.png)

---

## Findings & Insights

1) Do more skills get you better pay?
- There is a positive correlation between the number of skills listed in a job posting and median salary, especially visible in senior roles (e.g., Senior Data Engineer, Data Scientist).
- Roles with fewer required skills (e.g., Business Analyst) tend to have lower median salaries.
![Correlation chart](../images2/2_Project_Analysis_Chart1.png)

So what: Building a broader and deeper skill set can improve marketability and salary prospects, particularly for technical and senior roles.

2) Salary by region
- Senior Data Engineer and Data Scientist roles show higher median salaries both in the US and internationally.
- The US exhibits a noticeable salary premium for high-tech roles compared to non-US regions.
![Salary by region chart](../images2/2_Project_Analysis_Chart2.png)

So what: Geography matters—use these insights for salary negotiations and location-based career planning.

3) Top skills in data jobs
- SQL and Python appear as the most common and influential skills.
- Cloud technologies (AWS, Azure) and big data tools are also prevalent.
![Top skills chart](../images2/2_Project_Analysis_Chart3.png)

So what: Prioritize foundational programming and database skills, and complement them with cloud and engineering skills.

4) Pay for the top 10 skills
- High median salaries are associated with skills such as Python, Oracle, and SQL.
- Lower-paying / less-specialized skills include PowerPoint and Word.
![Top 10 skills vs pay chart](../images2/2_Project_Analysis_Chart4.png)

So what: Investing time in high-value technical skills (Python, SQL, cloud) yields better salary outcomes.

---

## Conclusion
Using Excel (Power Query + Power Pivot + DAX + PivotTables/Charts), this project highlights clear links between skills and compensation in the data job market. Multiple, specialized skills correlate with higher pay, and roles such as Senior Data Engineer and Data Scientist command higher median salaries—especially in the US. Python, SQL, and cloud expertise consistently appear as high-value skills.

---

## How to reproduce (short)
1. Open data_salary_all.xlsx.
2. Use Power Query to create and clean `data_jobs_all` and `data_job_skills` queries.
3. Load queries to the Data Model.
4. In Power Pivot create relationships on `job_id`.
5. Create DAX measures (see examples above).
6. Build PivotTables and PivotCharts to replicate the visuals.

---

If you'd like, I can:
- Translate the README fully into Uzbek.
- Produce a shorter one-page README for GitHub (badge-ready).
- Update image paths to match your repository structure exactly (provide the image filenames/locations).
Tell me which option you prefer and I’ll apply it.
