# HR Data Analysis - (MS SQL Server 2022 & PowerBI Project)

This project delves extensively into data analysis utilizing SQL and Power BI to reveal valuable human resource insights that can significantly enhance the company. Presenting visually appealing dashboards that provide essential HR metrics such as employee turnover, diversity, recruitment effectiveness, and performance evaluations. These tools assist HR professionals in making informed decisions and strategic workforce planning.

## Data Cleaning & Analysis Procedure
The data contains 23,000 employee record from year 2000 - 2020.
The following procedure was executed for data cleaning in Microsoft SQL 2022.

- Data import (MS Excel) into MS SQL Server & inspection
- Handled missing values
- Checked for missing values
- Ensured all data types in each column
- Data cleaning and analysis
  
## Power BI Visualisation
![Page-1](https://github.com/davidadabao/HR-Data-Project/blob/main/HR%20Data_Page_1.jpg)

![Page-2](https://github.com/davidadabao/HR-Data-Project/blob/main/HR%20Data_Page_2.jpg)

## Data Cleaning & Analysis Procedure
The data contains 23,000 employee record from year 2000 - 2020.

## Exploratory Data Analysis - EDA
### Queestions
1)	What's the age distribution in the company?
2)	What's the gender breakdown in the company?
3)	How does gender vary across departments and job titles?
4)	What's the race distribution in the company?
5)	What's the average length of employment in the company?
8)	How many employees work remotely for each department?
9)	What's the distribution of employees across different states?
10)	How are job titles distributed in the company?

### Findings:
1)	There are more male employees than female or non-conforming employees.
2)	The genders are fairly evenly distributed across departments. There are slightly more male employees overall.
3)	Employees 21-30 years old are the fewest in the company. Most employees are 31-50 years old. Surprisingly, the age group 50+ have the most employees in the company.
4)	Caucasian employees are the majority in the company, followed by mixed race, black, Asian, Hispanic, and native Americans.
5)	The average length of employment is 7 years.
6)	Auditing has the highest turnover rate, followed by Legal, Research & Development and Training. Business Development & Marketing have the lowest turnover rates.
7)	Employees tend to stay with the company for 6-8 years. Tenure is quite evenly distributed across departments.
8)	About 25% of employees work remotely.
9)	Most employees are in Ohio (14,788) followed distantly by Pennsylvania (930) and Illinois (730), Indiana (572), Michigan (569), Kentucky (375) and Wisconsin (321).
10)	There are 182 job titles in the company, with Research Assistant II taking most of the employees (634) and Assistant Professor, Marketing Manager, Office Assistant IV, Associate Professor and VP of Training and Development taking the just 1 employee each.
11)	Employee hire counts have increased over the years

### 1) Create Database
``` SQL
CREATE DATABASE hr;
```


