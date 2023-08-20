
Checking wich Campaign was accepted and wich not:

```
SELECT 
  AcceptedCmp1, 
  AcceptedCmp2, 
  AcceptedCmp3, 
  AcceptedCmp4, 
  AcceptedCmp5, 
  Response 
FROM 
  marketing_data;
```

---

Checking the total of Customers and How many said 'Yes' to every campaing:

```
SELECT 
  COUNT(ID) 
FROM 
  marketing_data; -- 2237

```
Campaign 1:
```
--1:
SELECT 
  COUNT(ID) as Succes1 
FROM 
  marketing_data 
WHERE 
  AcceptedCmp1 = 1 --143
;

SELECT 
  COUNT(ID) as NOSucces1 
FROM 
  marketing_data 
WHERE 
  AcceptedCmp1 = 0; --2094

```
Campaign 2:
```
--2:
SELECT 
  COUNT(ID) 
FROM 
  marketing_data 
WHERE 
  AcceptedCmp2 = 1 ;-- 30

```
Campaign 3:
```
--3:
SELECT 
  COUNT(ID) 
FROM 
  marketing_data 
WHERE 
  AcceptedCmp3 = 1; -- 163

```
Campaign 4:
```
--4:
SELECT 
  COUNT(ID) 
FROM 
  marketing_data 
WHERE 
  AcceptedCmp4 = 1; --167

```
Campaign 5:
```
--5:
SELECT 
  COUNT(ID) 
FROM 
  marketing_data 
WHERE 
  AcceptedCmp5 = 1; -- 162

```
Campaign R:
```
--Response:
SELECT 
  COUNT(ID) 
FROM 
  marketing_data 
WHERE 
  Response = 1 -- 333
;

SELECT 
  COUNT(ID) 
FROM 
  marketing_data 
WHERE 
  Response = 0; -- 1904

```
