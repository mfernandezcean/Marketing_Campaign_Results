


```

-- Income
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


-- YEAR
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

-- + Outliers:
SELECT DISTINCT Kidhome
FROM marketing_data -- vales go from 0 to 2. 

SELECT DISTINCT Teenhome
FROM marketing_data; -- vales go from 0 to 2. 


SELECT DISTINCT Dt_Customer
FROM marketing_data
ORDER BY 1 DESC ; -- Years go from 2012 an 2014. It seems ok

SELECT DISTINCT [Recency]
FROM marketing_data
ORDER BY [Recency]; -- 0 to 99 days since the last purchase. It seems ok

SELECT DISTINCT [MntWines]
FROM marketing_data
ORDER BY 1 DESC; -- No value seems to be problematic. 

SELECT DISTINCT [MntFruits]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [MntMeatProducts]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [MntFishProducts]
FROM marketing_data
ORDER BY 1 DESC;


SELECT DISTINCT [MntGoldProds]
FROM marketing_data
ORDER BY 1 DESC;


SELECT DISTINCT [NumDealsPurchases]
FROM marketing_data
ORDER BY 1 DESC;


SELECT DISTINCT [NumWebPurchases]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [NumCatalogPurchases]
FROM marketing_data
ORDER BY 1 DESC;


SELECT DISTINCT [NumStorePurchases]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [NumWebVisitsMonth]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [AcceptedCmp3]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [AcceptedCmp4]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [AcceptedCmp5]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [AcceptedCmp1]
FROM marketing_data
ORDER BY 1 DESC;


SELECT DISTINCT [AcceptedCmp2]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [Response]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [Complain]
FROM marketing_data
ORDER BY 1 DESC;

SELECT DISTINCT [Country]
FROM marketing_data
ORDER BY 1 DESC;


```
