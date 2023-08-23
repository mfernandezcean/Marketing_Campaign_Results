Total Transaction:

```
SELECT 
  (
    SUM(NumDealsPurchases) + SUM(NumWebPurchases) + SUM(NumCatalogPurchases) + SUM(NumStorePurchases)
  ) AS totalTransactions 
FROM 
  marketing_data; ----> 33.241

```
---

Amount Spended by Product Categorry:

```
SELECT 
  SUM(mntWines) AS WINE$, 
  SUM(MntFruits) AS FRUITS$, 
  SUM(MntMeatProducts) AS MEAT$, 
  SUM(MntFishProducts) AS FISH$, 
  SUM(MntSweetProducts) AS SWEET$, 
  SUM(MntGoldProds) AS GOLD$, 
  (
    SUM(mntWines) + SUM(MntFruits) + SUM(MntMeatProducts) + SUM(MntFishProducts) + SUM(MntSweetProducts) + SUM(MntGoldProds)
  ) AS Total_Spend 
FROM 
  marketing_data;

```
![wefgegwewgegwewgweg](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/9292aead-0e6d-4fc8-95fe-fb3991b0ec19)

---

Calculation the % of participation of Every Product in the Total:

```
WITH CategorySums AS (
  SELECT 
    SUM(mntWines) AS WINE$, 
    SUM(MntFruits) AS FRUITS$, 
    SUM(MntMeatProducts) AS MEAT$, 
    SUM(MntFishProducts) AS FISH$, 
    SUM(MntSweetProducts) AS SWEET$, 
    SUM(MntGoldProds) AS GOLD$, 
    SUM(
      mntWines + MntFruits + MntMeatProducts + MntFishProducts + MntSweetProducts + MntGoldProds
    ) AS Total_Spend 
  FROM 
    marketing_data
) 
SELECT 
  WINE$, 
  FRUITS$, 
  MEAT$, 
  FISH$, 
  SWEET$, 
  GOLD$, 
  Total_Spend, 
  (
    CAST(WINE$ AS DECIMAL) / Total_Spend
  ) * 100 AS WINE_Percentage, 
  -- WINE IS 50%
  (
    CAST(FRUITS$ AS DECIMAL) / Total_Spend
  ) * 100 AS FRUITS_Percentage, 
  -- Both combined are 78% of THE REVENUE 
  (
    CAST(MEAT$ AS DECIMAL) / Total_Spend
  ) * 100 AS MEAT_Percentage, 
  -- MEAT is 28% 
  (
    CAST(FISH$ AS DECIMAL) / Total_Spend
  ) * 100 AS FISH_Percentage, 
  (
    CAST(SWEET$ AS DECIMAL) / Total_Spend
  ) * 100 AS SWEET_Percentage, 
  (
    CAST(GOLD$ AS DECIMAL) / Total_Spend
  ) * 100 AS GOLD_Percentage 
FROM 
  CategorySums;

```

![dqwwqdwdqwdqwdq](https://github.com/mfernandezcean/Marketing_Campaign_Results/assets/105746149/c7c3338a-ef41-418f-8542-1caeb42df269)
