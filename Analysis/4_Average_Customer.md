-- What does the average customer look like?

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
