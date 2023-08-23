

Checking Education of Customers:

```
SELECT 
  Education, 
  COUNT(*) AS CustomersEducation 
FROM 
  marketing_data 
GROUP BY 
  Education;

```
![qwdwdqqwdqddwqqwd](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/ca544f9c-50ef-46da-a135-16a9544def58)

---

Checking Country of Customers:

```
SELECT 
  Country, 
  COUNT(*) AS _by_Country 
FROM 
  marketing_data 
GROUP BY 
  Country;

```

![fqwefqwfqwwq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/256b08f4-1711-4c2b-b552-70dee3d47168)

---

Checking Country = Spain & Education = Graduation
```
SELECT 
  COUNT(*) Count_Spain_Graduation 
FROM 
  marketing_data 
WHERE 
  Country = 'Spain' 
  AND Education = 'Graduation'

```

![qwdwqfwfqfwqwqwq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/4c7aea16-e338-4bdb-886e-0213961cbc8c)



