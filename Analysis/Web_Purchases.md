
- Did some checking with SQL but manly the information is on the Excel workbook

  Checked how the Wine Expenditure and the Web Purchases related:

```
SELECT 
  NumWebPurchases, 
  SUM(MntWines) as sum$wine 
FROM 
  marketing_data 
GROUP BY 
  NumWebPurchases 
ORDER BY 
  NumWebPurchases;
```
---

Cheked how the Age and the Web Purchades related:

```
SELECT 
  FLOOR(
    (
      YEAR(
        GETDATE()
      ) - Year_Birth
    ) / 10
  ) * 10 AS BirthYearInterval, 
  SUM(NumWebPurchases) AS Total_Web 
FROM 
  marketing_data 
GROUP BY 
  FLOOR(
    (
      YEAR(
        GETDATE()
      ) - Year_Birth
    ) / 10
  ) * 10 
ORDER BY 
  BirthYearInterval;

```

![qwdwdqdwqdqwdwq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/3102ee94-232a-4e6c-a657-0dd314fbe98b)
