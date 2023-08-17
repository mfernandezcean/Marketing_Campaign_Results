
First me check the whole table:

```
SELECT *
FROM marketing_data
```
### Nulls:
```
SELECT 
  Education, 
  Income 
FROM 
  marketing_data 
WHERE 
  Income IS NULL;
```
Using Union to check for other Null Values: 
```


SELECT ID AS TableName, *
FROM marketing_data
WHERE ID IS NULL
UNION ALL
SELECT Income AS TableName, *
FROM marketing_data
WHERE Income IS NULL
UNION
SELECT [Marital_Status] AS TableName, *
FROM marketing_data
WHERE [Marital_Status] IS NULL
UNION
SELECT [Country] AS TableName, *
FROM marketing_data
WHERE [Country] IS NULL
```
- After Checking the Table, the Null values we've got are the 24 rows of [Income]
```
SELECT 
[Education],
AVG(INCOME) AS avg_income
FROM marketing_data
GROUP BY [Education]

SELECT AVG(income) AVGofincome
FROM marketing_data;

WITH cte1 As
(
SELECT 
	ID,
    Education,
    CASE 
        WHEN Education = 'Graduation' AND Income IS NULL THEN 52720 
        WHEN Education = 'PhD' AND Income IS NULL THEN 56145
		WHEN Education = 'Master' AND Income IS NULL THEN 52917
		WHEN Education = '2n Cycle' AND Income IS NULL THEN 47633
		WHEN Education = 'Basic' AND Income IS NULL THEN 20306  
        ELSE Income 
    END AS INCOME 
FROM marketing_data
WHERE Income IS NULL 
)

SELECT -- ID,
Marital_Status,
AVG(INCOME)
FROM marketing_data
GROUP BY Marital_Status 

SELECT Marital_Status, COUNT(ID) as count_
FROM marketing_data
GROUP BY Marital_Status;


SELECT Education, COUNT(ID) as count_
FROM marketing_data
GROUP BY Education
ORDER BY 1 ASC; 

SELECT Education, Income
FROM marketing_data
WHERE Income IS NOT NULL 
ORDER BY Income ASC
 
```

-- Outliers
```
SELECT 
ID,
Education,
Marital_Status,
Income,
(Income- AVG(Income) OVER()) / STDEV(Income) OVER() AS zscore 
FROM marketing_data
ORDER BY ID

Select *
FROM
(SELECT 
ID,
Education,
Marital_Status,
Income,
(Income- AVG(Income) OVER()) / STDEV(Income) OVER() AS zscore 
FROM marketing_data
) AS score_table
WHERE zscore > 2.576 or zscore <-2.576  

Select *
FROM
(SELECT 
ID,
Education,
Marital_Status,
Income,
(Income- AVG(Income) OVER()) / STDEV(Income) OVER() AS zscore 
FROM marketing_data
) AS score_table
WHERE zscore > 1.960 or zscore <-1.960  





SELECT Income
FROM marketing_data
WHERE Income IS NOT NULL
AND ABS((Income - (SELECT AVG(Income) FROM marketing_data)) / (SELECT STDEV(Income) FROM marketing_data)) > 5;

SELECT Income
FROM marketing_data
WHERE Income > PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY Income) OVER();

Select *
FROM
(SELECT 
ID,
Year_Birth,
Education,
Marital_Status,
Income,
(Year_Birth- AVG(Year_Birth) OVER()) / STDEV(Year_Birth) OVER() AS zscore 
FROM marketing_data
) AS score_table
WHERE zscore > 2.576 or zscore <-2.576  

```
