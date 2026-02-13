**Overview**

This project implements a complete data engineering pipeline for hotel booking analytics using Snowflake as the core data platform. The pipeline follows the medallion architecture pattern (Bronze-Silver-Gold) to transform raw booking data into actionable business insights, visualized through interactive dashboards.

***Key Business Questions Answered:***

What is our daily booking volume and revenue?

Which cities generate the most revenue?

What are the monthly booking trends?

What is the average booking value?

**Architecture**

<img width="1400" height="1000" alt="Blank diagram" src="https://github.com/user-attachments/assets/aa7ff4e1-a4ab-408b-898d-2b96f6eb97de" />

**Getting Started**

***Prerequisites:***

Snowflake account (trial or paid)

Basic SQL knowledge

Sample CSV data files

***Data Flow:***

Raw CSV files → Staged in Snowflake

Bronze Layer → Raw data ingestion (preserved original state)

Silver Layer → Data cleaning, validation, and standardization

Gold Layer → Business aggregations and KPIs

Snowsight Dashboard → Interactive visualizations

**Technologies Used**

Snowflake	 -  Cloud data warehouse

SQL	Data   -  Transformation and modeling

Snowsight	 -  Dashboarding and visualization

Git/GitHub -  Version control and project sharing

CSV	Source -  Data format

**Data Quality Rules**

***The silver layer implements several data quality checks:***

Email validation       - LIKE '%@%.%' pattern matching

Date validation	       - TRY_TO_DATE() with NULL checks

Logical date order     - Check_out_date >= check_in_date

Positive amounts       - ABS() function

String standardization - INITCAP(), TRIM(), LOWER()

Currency code format   -	UPPER() with TRIM

Status typo correction - CASE statement for common misspellings

<img width="1920" height="916" alt="Screenshot (607)" src="https://github.com/user-attachments/assets/2cb52072-c369-41af-a493-afff56226bdf" />


**Dashboard Preview**

<img width="1902" height="915" alt="Screenshot (606)" src="https://github.com/user-attachments/assets/dd8eb963-e892-489b-8852-823d6d1f0ae5" />


***Dashboard Components:***

Total Bookings - Overall booking count

Total Revenue - Sum of all booking amounts

Average Booking Value - Revenue per booking

Total Guests - Sum of guests across all bookings

