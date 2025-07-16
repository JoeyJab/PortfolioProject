# PortfolioProject
All personal SQL Projects
This project explores global layoffs data using SQL to clean, structure, and analyze real-world trends. It demonstrates my ability to perform end-to-end data analysis using raw datasets — from cleaning and transformation to insights and ranking logic.

--Skills Demonstrated are
MySQL syntax
Data cleaning (handling nulls, duplicates, formatting)
CTEs, window functions (ROW_NUMBER, DENSE_RANK)
Aggregation and grouping (e.g., total layoffs by industry, country, year)
Date transformation and trend analysis
Analytical thinking and exploration of business-relevant insights

--The dataset contains records of tech and startup layoffs globally, including:
Company
Location
Industry
Total laid off
Percentage laid off
Stage of funding
Date of layoff
Country
Funds raised

--Data Cleaning Process
1. Remove Duplicates
Used ROW_NUMBER() in a CTE to identify duplicates based on a combination of company name, location, industry, layoffs, and other identifying fields, then removed them from a staging table.

2. Standardize Data
Trimmed extra spaces in text fields
Unified inconsistent industry names (e.g., "Crypto" vs "crypto & web3")
Removed punctuation inconsistencies in country names

3. Fix Date Format
Converted text-based date field to DATE type using STR_TO_DATE()
Extracted year and month for time-based analysis

4. Handle Nulls
Updated missing industries by joining the table to itself based on company name
Removed rows where both total_laid_off and percentage_laid_off were missing (non-informative)

5. Drop Unnecessary Columns
Removed temporary columns like row_num after processing


--Key Questions Explored:
Which companies had the largest total layoffs?
Which industries were most affected?
How did layoffs trend over time (monthly, yearly)?
Which stages (early, late, IPO) saw the highest layoffs?
Which countries were hit hardestKey Questions Explored:
Which companies had the largest total layoffs?
Which industries were most affected?
How did layoffs trend over time (monthly, yearly)?
Which stages (early, late, IPO) saw the highest layoffs?
Which countries were hit hardest?
What were the top 5 companies with the most layoffs each year?


--Techniques Used:
GROUP BY, SUM(), MIN(), MAX()
1.Time-based grouping using SUBSTRING(date, 1, 7)
2.Rolling totals with OVER(ORDER BY ...)
3.Yearly rankings using DENSE_RANK() in CTEs
4.What were the top 5 companies with the most layoffs each year?


--Key Insights
1.Some companies laid off 100% of their staff, often despite raising significant funding
2.The tech sector and crypto startups were heavily affected
3.Layoffs peaked at specific points in the year, showing clear waves
4.A small number of companies account for the largest layoff events globally


--What I Learned
1.How to structure and optimize SQL queries for real-world business data
2.Practical handling of messy text data (like inconsistent names and formats)
3.Advanced use of CTEs and ranking functions
4.Importance of a clean dataset before doing any meaningful analysis

