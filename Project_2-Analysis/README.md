# Project 2 Analysis

## Introduction

As someone transitioning into a data analyst role, I wanted to sharpen my Excel analytics skills while exploring what employers really value in data-related careers. I enrolled in [Luke Barousse's Excel course](https://www.lukebarousse.com/excel) and took on this project to not only practice technical skills but also gain insight into how skills align with salary trends in the job market.

This hands-on project allowed me to explore a real-world dataset from 2023 and apply essential Excel features to answer key questions relevant to job seekers and hiring managers alike.

### Project Goals

I approached the dataset with these questions in mind:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Practical Skills Utilized 

Through this analysis, I gained practical experience using:
    
 - **Pivot Tables** – for summarizing and grouping data efficiently
 - **Pivot Charts** – to visualize trends and comparisons
 - **DAX (Data Analysis Expressions)** – for custom calculations
 - **Power Query** – to clean, transform, and load structured data
 - **Power Pivot** – to create a scalable data model

This project solidified my comfort with Excel’s data modeling ecosystem and helped me think more analytically when approaching business questions.

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The data is from the [Luke Barousse Excel course](https://www.lukebarousse.com/excel), which provides a foundation for analyzing data using Excel. 

## 1️⃣ Do more skills get you better pay?

### Focus: Using Power Query to Prep Data

- #### Extract & Transform

     I created two queries: one with full job data and another with job ID-to-skill mappings. Using transformation steps, I:
    - Converted column types and cleaned inconsistent text
    - Removed irrelevant columns
    -  Normalized data for analysis (e.g., trimming whitespace)
          
- data_jobs_all

  ![2_Project_Analysis_Screenshot1](https://github.com/user-attachments/assets/e4699d69-9def-4816-a332-45dbf5ac45fa)
  
- data_job_skills

  ![2_Project_Analysis_Screenshot2](https://github.com/user-attachments/assets/be8990d6-1e11-4e9f-89eb-1ce6220a083e)

This process helped me appreciate how clean data fuels better analysis—a key takeaway I’ll apply in any analytics role.

- #### Load

     Once cleaned, I loaded both tables into Excel’s data model for deeper analysis with PivotTables and DAX.

    - data_jobs_all
        ![2_Project_Analysis_Screenshot3](https://github.com/user-attachments/assets/589b40b2-d63c-4dc3-b649-e36313072918)
    
    - data_job_skills
       ![2_Project_Analysis_Screenshot4](https://github.com/user-attachments/assets/e0ec834f-42c1-4583-a6b3-230797d18d09)


### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

   ![2_Project_Analysis_Chart1](https://github.com/user-attachments/assets/5cb0fc6a-5c7b-443c-97d4-77d4d0fe1ccd)


#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

   ![2_Project_Analysis_Chart2](https://github.com/user-attachments/assets/9afa4464-8323-4ebe-80ce-9217c826443c)


#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

   ![2_Project_Analysis_Screenshot5](https://github.com/user-attachments/assets/764ca393-dc91-4010-9d05-f9688049ce8d)


#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

   ![2_Project_Analysis_Screenshot6](https://github.com/user-attachments/assets/f3faaa96-eeed-4817-af37-d98a8b2f09f5)


### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3](https://github.com/user-attachments/assets/2ffe843d-a107-4a70-bba7-3a43549895f2)


#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

   ![2_Project_Analysis_Chart4](https://github.com/user-attachments/assets/04773086-a2ef-424b-b140-6592ce5e1276)


### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

As a data enthusiast and job seeker, I embarked on this Excel-based project to uncover valuable insights about the data science job market and learn advanced Excel skills for data analytics. Using a dataset from real-world job postings provided by [Luke Barousse Excel course](https://www.lukebarousse.com/excel), I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
