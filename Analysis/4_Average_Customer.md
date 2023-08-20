

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
![dwqqwdqwdqwdqwdqwddwq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/7775fd8a-de44-4511-9b7d-7c45f64a5cee)

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

![wfqfwqfwqfwq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/ca007cfb-5c8f-4cfd-beef-61168f8e4087)

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

![wdqdqwdwqdwqdwq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/a1fb8a05-7739-4a2c-8104-30e4a2954e24)


```
