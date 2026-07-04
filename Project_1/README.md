# Excel Salary Dashboard

<img src="../images_and_gifs/1_Salary_Dashboard_Final_Dashboard.gif" width="600" alt="Dashboard Preview">

## 📖 Project Overview

This project was completed as part of **Luke Barousse's Excel for Data Analytics course**, where I recreated an interactive salary dashboard using Microsoft Excel. While following the guided project, I gained hands-on experience building data visualizations and interactive reporting tools.

Using **2,400+ real-world data science job postings from 2023**, the dashboard enables users to explore salary trends across job titles, countries, and employment types. It provides an interactive way to benchmark salaries and make informed career decisions.

---

## 📂 Dashboard File

The completed dashboard is available here:

**[Job_Market_Analysis.xlsx](Job_Market_Analysis.xlsx)**

---

## 🎯 Skills Demonstrated

- Dashboard Design
- Data Visualization
- Dynamic Array Formulas
- Data Validation
- Interactive Reporting
- Business Insight Generation

---

## 🛠️ Excel Features Used

| Feature | Purpose |
|---------|---------|
| 📉 Charts | Visualize salary comparisons and geographic trends |
| 🧮 Formulas & Functions | Perform dynamic salary calculations |
| ❎ Data Validation | Create interactive dropdown filters |

---

## 📊 Dataset

The dashboard uses a dataset containing **2,400+ real-world data science job postings from 2023**, provided as part of the Excel course.

The dataset includes:

- 👨‍💼 Job Titles
- 💰 Annual Salaries
- 📍 Countries
- 💼 Employment Types
- 🛠️ Required Skills

---

# ⚙️ Dashboard Implementation

## 📉 Data Science Job Salaries

<img src="../images_and_gifs/1_Salary_Dashboard_Chart1.png" width="350" alt="Bar Chart">

### Purpose

Compare median salaries across different data-related job titles.

### Excel Features Used

- Horizontal Bar Chart
- Custom Number Formatting
- Data Sorting

### Key Insight

Senior-level positions and engineering roles command considerably higher median salaries than analyst positions, making salary differences easy to identify at a glance.

---

## 🗺️ Country Median Salaries

<img src="../images_and_gifs/1_Salary_Dashboard_Country_Map.gif" width="350" alt="Map Chart">

### Purpose

Visualize how salaries vary across different countries.

### Excel Features Used

- Map Chart
- Conditional Color Scaling

### Key Insight

The dashboard quickly highlights geographic salary disparities, with countries such as the United States and Canada generally offering higher median salaries than many other regions.

---

# 🧮 Formulas and Functions

## 💰 Median Salary Calculation

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

### What it does

Calculates the median salary after filtering by:

- Job Title
- Country
- Employment Type

while excluding empty salary values.

### Why it matters

Using an array formula allows the dashboard to update dynamically whenever the user changes a dropdown selection, eliminating the need for manual recalculation or multiple PivotTables.

#### Background Table

<img src="../images_and_gifs/1_Salary_Dashboard_Screenshot1.png" width="300" alt="Background Table">

#### Dashboard Result

<img src="../images_and_gifs/1_Salary_Dashboard_Job_Title.png" width="300" alt="Dashboard Result">

---

## ⏰ Dynamic Schedule Type List

```excel
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

### What it does

Creates a clean list of valid employment types by removing invalid or combined entries.

### Why it matters

The generated list serves as the source for the dashboard's dropdown filter, ensuring users only select valid options.

#### Background Table

<img src="../images_and_gifs/1_Salary_Dashboard_Screenshot2.png" width="300" alt="Background Table">

#### Dashboard Result

<img src="../images_and_gifs/1_Salary_Dashboard_Type.png" width="300" alt="Dashboard Result">

---

# ✅ Data Validation

## Interactive Filters

The dashboard uses Excel Data Validation to create dropdown menus for:

- Job Title
- Country
- Employment Type

### Benefits

- Prevents invalid user input
- Improves dashboard usability
- Creates a more interactive experience

<img src="../images_and_gifs/1_Salary_Dashboard_Data_Validation%20(1).gif" width="350" alt="Data Validation">

---

# 📚 Key Takeaways

Through this project I gained practical experience with:

- Designing interactive Excel dashboards
- Building dynamic calculations using array formulas
- Creating user-friendly dropdown filters
- Presenting insights through effective visualizations
- Organizing data for better decision-making

---

# 🏁 Conclusion

This project demonstrates how Microsoft Excel can transform raw job market data into an interactive dashboard that supports salary benchmarking and career exploration.

Although the dashboard was built as a guided project while completing **Luke Barousse's Excel for Data Analytics course**, recreating it provided valuable hands-on experience with dashboard design, dynamic formulas, and data visualization techniques.

---

# 🚀 Future Improvements

Potential enhancements include:

- Add experience-level comparisons
- Display salary percentiles
- Compare multiple countries simultaneously
- Build a Power BI version of the dashboard
- Connect to live job market datasets

---

# 💬 Contact

If you have suggestions or feedback, feel free to reach out.

- 💼 LinkedIn: *(Add your LinkedIn profile)*
- 📧 Email: *(Add your email address)*

⭐ If you found this project useful, consider giving the repository a star!
