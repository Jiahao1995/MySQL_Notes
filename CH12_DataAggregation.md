# 汇总数据

## 聚集函数
- AVG()
- COUNT()
- MAX()
- MIN()
- SUM()

### AVG() 函数
```mysql
SELECT AVG(prod_price) AS avg_price
FROM products;
->
+-----------+
| avg_price |
+-----------+
| 16.133571 |
+-----------+
<-
```

### COUNT() 函数
对所有行计数
```mysql
SELECT COUNT(*) AS num_cust
FROM customers;
->
+----------+
| num_cust |
+----------+
|        5 |
+----------+
<-

SELECT cust_email FROM customers;
->
+---------------------+
| cust_email          |
+---------------------+
| ylee@coyote.com     |
| NULL                |
| rabbit@wascally.com |
| sam@yosemite.com    |
| NULL                |
+---------------------+
<-

SELECT COUNT(cust_email) AS num_cust
FROM customers;
->
+----------+
| num_cust |
+----------+
|        3 |
+----------+
<-
```

### MAX() 函数

### MIN() 函数

### SUM() 函数

## 聚集不同值
```mysql
SELECT AVG(DISTINCT prod_price) AS avg_price
FROM products
WHERE vend_id = 1003;
->
+-----------+
| avg_price |
+-----------+
| 15.998000 |
+-----------+
<-
```

## 组合聚集函数
```mysql
SELECT COUNT(*) AS num_items,
       MIN(prod_price) AS price_min,
       MAX(prod_price) AS price_max,
       AVG(prod_price) AS price_avg
FROM products;
->
+-----------+-----------+-----------+-----------+
| num_items | price_min | price_max | price_avg |
+-----------+-----------+-----------+-----------+
|        14 |      2.50 |     55.00 | 16.133571 |
+-----------+-----------+-----------+-----------+
<-
```

