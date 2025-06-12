# Project 1: Excel Salary Dashboard

![Final Dashboard](https://github.com/user-attachments/assets/12280e08-ef13-4360-b4a8-e0c958bbb3a3)

## Introduction

As someone actively transitioning into a data analyst role, I created this dashboard to better understand salary trends across the data job market—and to put into practice the Excel skills I’ve gained through hands-on learning.

This [project](https://github.com/sland587/Excel_Project-Data_Analytics/raw/main/Project_1-Dashboard/Salary_Dashboard.xlsx) is based on a dataset provided by the [Luke Barousse's Excel for Data Analytics course](https://www.lukebarousse.com/excel), which helped solidify my understanding of Excel as a powerful tool for data analysis. The dashboard provides a clean, interactive view of salaries by job title, location, and work type, tailored for job seekers like myself to make informed career decisions.

### Project Goals

The goal of this project was to create a user-friendly dashboard that provides insight into data job salaries across different countries, job titles, and work schedules. The dashboard enables users to:

- Explore global and role-based salary patterns
- Identify high-paying job titles and regions
- Interact with a clean, dynamic interface using validated filters

This project helped reinforce my understanding of Excel for data analytics and dashboard design.

### Practical Skills Utilized

Through this analysis, I gained practical experience using:

- **Charts** – for visual storytelling of data  
- **Formulas & Functions** – to generate flexible, dynamic insights  
- **Data Validation** – to improve user experience and dashboard reliability

### Data Jobs Dataset
The dataset used in this project was provided as part of the [Luke Barousse's Excel for Data Analytics course](https://www.lukebarousse.com/excel) and includes real-world data science job information from 2023.

## Dashboard Build Process

### Charts

- #### Job Title Salary Comparison (Bar Chart)

<img src="https://github.com/user-attachments/assets/0b7bcfc5-bb8c-457f-be8b-6b5f9d6faa55" width="850" height="550" alt="Job Salary Bar Chart">



#### Analysis & Reflection

##### Insights
To visualize salary differences clearly, I used a horizontal bar chart sorted by descending salary. This approach helps quickly spot which roles such as **Senior Data Engineers** and **Data Scientists** consistently offer higher pay.

##### Takeaway
Good design choices can enhance clarity. Sorting and formatting really matter when building dashboards people will rely on.

- #### Median Salary by Country (Map Chart)

![Map Chart](https://github.com/user-attachments/assets/f79ddb88-0bf3-4627-b7d6-c7b777642dd5)

The map chart gave me a clearer view of geographic salary trends. I color-coded salary ranges to reveal disparities across countries.

> **What I Learned**: Even with the same job titles, location can heavily impact salary—something this chart makes instantly obvious.

---

### Formulas and Functions

#### Median Salary by Job Criteria

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
