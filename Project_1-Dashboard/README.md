# Excel Salary Dashboard

![1_Salary_Dashboard_Final_Dashboard](https://github.com/user-attachments/assets/12280e08-ef13-4360-b4a8-e0c958bbb3a3)


## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

The data is from the [Luke Barousse Excel course](https://www.lukebarousse.com/excel), which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [Salary_Dashboard.xlsx](https://github.com/sland587/Excel_Project-Data_Analytics/raw/main/Project_1-Dashboard/Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023 provided by the [Excel for Data Analytics course](https://www.lukebarousse.com/excel). It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

### Charts

#### Data Science Job Salaries - Bar Chart

<img src="https://github.com/user-attachments/assets/0b7bcfc5-bb8c-457f-be8b-6b5f9d6faa55" width="850" height="550" alt="Salary Dashboard Chart1">

- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart
![1_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/f79ddb88-0bf3-4627-b7d6-c7b777642dd5)

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- **Data Representation:** Plotted median salary for each country with available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

#### Median Salary by Job Titles

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

- **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table

![1_Salary_Dashboard_Screenshot1](https://github.com/user-attachments/assets/dc207113-4db5-4e51-9eae-ccc3fb71e4fa)

Dashboard Implementation

<img src="https://github.com/user-attachments/assets/6d998b82-1694-4a4d-aae1-efd628aedf43" width="400" height="500" alt="Salary Dashboard Title">

#### Count of Job Schedule Type

- **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
 ```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```
- **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

Background Table

![1_Salary_Dashboard_Screenshot2](https://github.com/user-attachments/assets/17d94566-c87d-4218-81bf-e4ee8496c40d)


Dashboard Implementation:

<img src="https://github.com/user-attachments/assets/8b075d39-05c4-45b7-8031-71d96745a565" width="350" height="500" alt="Salary Dashboard Type">

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced

<img src="https://github.com/user-attachments/assets/fb50fe45-bde9-48ad-9246-a728ea3d3c88"  width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from the  [Luke Barousse Excel course](https://www.lukebarousse.com/excel), this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
