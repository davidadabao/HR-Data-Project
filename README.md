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

## Data Preview
![Page-1](https://github.com/davidadabao/HR-Data-Project/blob/main/1.JPG)

![Page-2](https://github.com/davidadabao/HR-Data-Project/blob/main/2.JPG)

The data contains 23,000 employee record from year 2000 - 2020.

## Exploratory Data Analysis - EDA
### Questions
1)	How many employees work remotely for each department? 
2)	What's the race distribution in the company? 
3)	What's the biggest department with highest number of employees?
4)	What's the age distribution in the company?
5)	What's the gender breakdown in the company?
6)	What's the age distribution by gender in the company?
7)	What's the distribution of employees across different states?

### Findings:
1)	About 75% of the company's employees work at the headquarters, while 25% work remotely.
2)	White employees are the majority in the company, followed by mixed-race, Black Africans, Asians, Hispanics, and Native Americans.
3)	The Engineering department has the highest number of employees, followed by Accounting, human Resource, Sales, Training, Services, Business Development, Research & Development, Support, Product Management, Marketing, Legal and Auditing.
4)	Employees from the age of 50 and above have the most employees in the company. Seconded by age between 41 and 50 years old. Most employees are between 31 and 40 years old. The age range of 21–30 years old is the fewest in the company.
5)	Gender seems to be on an equal level between males and females, but male employees seem to be a little bit higher than females.
6)	Male and female employees from the age of 50 and above have the highest difference of 389, followed by those between 41 and 50 with a difference of 300. Next is age between 31 and 30 with a difference of 197, followed by ages between 22 and 30 with a difference of 13.
7)	Most employees are in Ohio (14,788) followed distantly by Pennsylvania (930) and Illinois (730), Indiana (572), Michigan (569), Kentucky (375) and Wisconsin (321).

## SQL Command lines

### 1. Create Database
``` SQL
CREATE DATABASE hr
```
### 2. Import Data to SQL Server
- Use import wizard to import HR Data.csv to hr table.
- Inspect data types before importing into MS SQL Server.

``` SQL
SELECT * FROM hr_data
```
## QUESTIONS TO GET FROM THE DATA

#### 1) How many employees work remotely for each department?

``` SQL
SELECT location,
count(*) as count FROM hr_data
WHERE new_termdate IS NULL
GROUP BY location
```

#### 2) What's the race distribution in the company?

``` SQL
SELECT race,
count(*) AS count FROM hr_data
WHERE new_termdate IS NULL 
GROUP BY race
ORDER BY count DESC
```

#### 3) How does gender vary across departments and job titles?

``` SQL
SELECT 
department,
gender,
count(gender) AS count
FROM hr_data
WHERE new_termdate IS NULL
GROUP BY department, gender,
ORDER BY department, gender ASC
```
- Job Titles

``` SQL
SELECT 
department, jobtitle,
gender,
count(gender) AS count
FROM hr_data
WHERE new_termdate IS NULL
GROUP BY department, jobtitle, gender
ORDER BY department, jobtitle, gender ASC
```

#### 4) What's the age distribution in the company?

``` SQL
SELECT
MIN(age) AS youngest,
MAX(age) AS OLDEST
FROM hr_data
```
- Age group count

``` SQL
SELECT age_group, count(*) AS count
FROM
(SELECT 
 CASE
  WHEN age <= 21 AND age <= 30 THEN '21 to 30'
  WHEN age <= 31 AND age <= 40 THEN '31 to 40'
  WHEN age <= 41 AND age <= 50 THEN '41 to 50'
  ELSE '50+'
  END AS age_group
 FROM hr_data
 WHERE new_termdate IS NULL
 ) AS subquery
GROUP BY age_group
ORDER BY age_group
```

#### 5) What's the gender breakdown in the company?

``` SQL
SELECT
 gender,
 COUNT(gender) AS count
FROM hr_data
WHERE new_termdate IS NULL
GROUP BY gender
ORDER BY gender ASC
```

#### 6) What's the age distribution by gender in the company?

``` SQL
SELECT age_group, gender,
count(*) AS count
FROM
(SELECT 
 CASE
  WHEN age <= 21 AND age <= 30 THEN '21 to 30'
  WHEN age <= 31 AND age <= 40 THEN '31 to 40'
  WHEN age <= 41 AND age <= 50 THEN '41 to 50'
  ELSE '50+'
  END AS age_group,
  gender
 FROM hr_data
 WHERE new_termdate IS NULL
 ) AS subquery
GROUP BY age_group, gender
ORDER BY age_group, gender
```

#### 7) What's the distribution of employees across different states?

``` SQL
SELECT location_state,
count(*) AS count
FROM hr_data
WHERE new_termdate IS NULL
GROUP BY location_state
ORDER BY count DESC
```
