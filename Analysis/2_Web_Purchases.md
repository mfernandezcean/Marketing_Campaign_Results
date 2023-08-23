
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
![erhehrtreth](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/780e6c15-032e-4340-82f4-79bcbe3e52bf)

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

![fwqefwweft23w](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/416a8b17-d2ba-4596-9ea4-1d9f0c0f956e)

---

Cheked how the Complain and the Web Purchades related:

```
SELECT 
  Complain, 
  SUM(NumWebPurchases) AS Number_of_WebPurhcases 
FROM 
  marketing_data 
GROUP BY 
  Complain;

```

![ewfgewfefefefwefwewf](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/11fa7362-f6d6-40de-be3a-b2b0b645f7b7)

---

Cheked how the Number of Visits per Month and the Web Purchades related:

```
SELECT 
  NumWebVisitsMonth, 
  SUM(NumWebPurchases) AS Number_of_WebPurhcases 
FROM 
  marketing_data 
GROUP BY 
  NumWebVisitsMonth 
ORDER BY 
  2 desc;

```

![3g4e4weg3w4qe](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/1a9df818-40fd-4496-8530-998d3c2b074a)
