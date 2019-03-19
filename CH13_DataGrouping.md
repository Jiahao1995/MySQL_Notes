# 分组数据

## 创建分组
```mysql
SELECT vend_id FROM products;
->
+---------+
| vend_id |
+---------+
|    1001 |
|    1001 |
|    1001 |
|    1002 |
|    1002 |
|    1003 |
|    1003 |
|    1003 |
|    1003 |
|    1003 |
|    1003 |
|    1003 |
|    1005 |
|    1005 |
+---------+
<-

SELECT vend_id, COUNT(*) AS num_prods
FROM products
GROUP BY vend_id;
->
+---------+-----------+
| vend_id | num_prods |
+---------+-----------+
|    1001 |         3 |
|    1002 |         2 |
|    1003 |         7 |
|    1005 |         2 |
+---------+-----------+
<-

SELECT vend_id, COUNT(*) AS num_prods
FROM products
GROUP BY vend_id WITH ROLLUP;
->
+---------+-----------+
| vend_id | num_prods |
+---------+-----------+
|    1001 |         3 |
|    1002 |         2 |
|    1003 |         7 |
|    1005 |         2 |
|    NULL |        14 |
+---------+-----------+
<-
```

## 过滤分组
```mysql
SELECT vend_id, COUNT(*) AS orders
FROM products
GROUP BY vend_id
HAVING COUNT(*) > 2;
->
+---------+--------+
| vend_id | orders |
+---------+--------+
|    1001 |      3 |
|    1003 |      7 |
+---------+--------+
<-
```

### WHERE 和 HAVING 的区别
```mysql
SELECT vend_id, prod_price FROM products;
->
+---------+------------+
| vend_id | prod_price |
+---------+------------+
|    1001 |       5.99 |
|    1001 |       9.99 |
|    1001 |      14.99 |
|    1003 |      13.00 |
|    1003 |      10.00 |
|    1003 |       2.50 |
|    1002 |       3.42 |
|    1005 |      35.00 |
|    1005 |      55.00 |
|    1002 |       8.99 |
|    1003 |      50.00 |
|    1003 |       4.49 |
|    1003 |       2.50 |
|    1003 |      10.00 |
+---------+------------+
<-

SELECT vend_id, prod_price
FROM products
WHERE prod_price >= 10;
->
+---------+------------+
| vend_id | prod_price |
+---------+------------+
|    1001 |      14.99 |
|    1003 |      13.00 |
|    1003 |      10.00 |
|    1005 |      35.00 |
|    1005 |      55.00 |
|    1003 |      50.00 |
|    1003 |      10.00 |
+---------+------------+
<-

SELECT vend_id, COUNT(*) AS num_prods
FROM products
WHERE prod_price >= 10
GROUP BY vend_id
HAVING COUNT(*) >= 2;
->
+---------+-----------+
| vend_id | num_prods |
+---------+-----------+
|    1003 |         4 |
|    1005 |         2 |
+---------+-----------+
<-
```

## SELECT 字句顺序
1. SELECT
2. FROM
3. WHERE
4. GROUP BY
5. HAVING
6. ORDER BY
7. LIMIT
