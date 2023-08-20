
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
![dqwwdqwdqqwqwd](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/f3bd291a-7079-416e-b787-b21d6a93f95e)

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

![qwdqwddqwdqwdqw](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/cfc8da03-02f8-4f7d-8f5c-c6828f576c9b)

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

![d32d2d32d](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/ebe61d9a-3b4a-4628-8364-1ac727207236)
