# Group-Sold-Products-By-The-Date
## Problem Link
[Group Sold Products By The Date- LeetCode](https://leetcode.com/problems/group-sold-products-by-the-date/description/?envType=study-plan-v2&envId=top-sql-50)
## Solution
```sql
select  sell_date
, count( product) num_sold
,STRING_AGG(product,',') 
        WITHIN GROUP (ORDER BY product) products
from(SELECT DISTINCT * FROM Activities) p
group by p.sell_date
