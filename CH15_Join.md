# 联结表

## 创建联结

```mysql
SELECT vend_id, vend_name
FROM vendors;
->
+---------+----------------+
| vend_id | vend_name      |
+---------+----------------+
|    1001 | Anvils R Us    |
|    1002 | LT Supplies    |
|    1003 | ACME           |
|    1004 | Furball Inc.   |
|    1005 | Jet Set        |
|    1006 | Jouets Et Ours |
+---------+----------------+
<-

SELECT vend_id, prod_name
FROM products;
->
+---------+----------------+
| vend_id | prod_name      |
+---------+----------------+
|    1001 | .5 ton anvil   |
|    1001 | 1 ton anvil    |
|    1001 | 2 ton anvil    |
|    1003 | Detonator      |
|    1003 | Bird seed      |
|    1003 | Carrots        |
|    1002 | Fuses          |
|    1005 | JetPack 1000   |
|    1005 | JetPack 2000   |
|    1002 | Oil can        |
|    1003 | Safe           |
|    1003 | Sling          |
|    1003 | TNT (1 stick)  |
|    1003 | TNT (5 sticks) |
+---------+----------------+
<-


SELECT vend_name, prod_name, prod_price
FROM vendors, products
WHERE vendors.vend_id = products.vend_id
ORDER BY vend_name, prod_name;
->
+-------------+----------------+------------+
| vend_name   | prod_name      | prod_price |
+-------------+----------------+------------+
| ACME        | Bird seed      |      10.00 |
| ACME        | Carrots        |       2.50 |
| ACME        | Detonator      |      13.00 |
| ACME        | Safe           |      50.00 |
| ACME        | Sling          |       4.49 |
| ACME        | TNT (1 stick)  |       2.50 |
| ACME        | TNT (5 sticks) |      10.00 |
| Anvils R Us | .5 ton anvil   |       5.99 |
| Anvils R Us | 1 ton anvil    |       9.99 |
| Anvils R Us | 2 ton anvil    |      14.99 |
| Jet Set     | JetPack 1000   |      35.00 |
| Jet Set     | JetPack 2000   |      55.00 |
| LT Supplies | Fuses          |       3.42 |
| LT Supplies | Oil can        |       8.99 |
+-------------+----------------+------------+
<-
```
要保证所有联结都有 WHERE 子句，同时保证其正确性

### 内部联结
另一种语法：
```mysql
SELECT vend_name, prod_name, prod_price
FROM vendors INNER JOIN products
ON vendors.vend_id = products.vend_id;
```
INNER JOIN 是联结**两个表**的规范语法，确保不会忘记联结条件，性能更优

### 联结多个表
```mysql
SELECT prod_name, vend_name, prod_price, quantity
FROM orderitems, products, vendors
WHERE products.vend_id = vendors.vend_id
AND orderitems.prod_id = products.prod_id
AND order_num = 20005;
->
+----------------+-------------+------------+----------+
| prod_name      | vend_name   | prod_price | quantity |
+----------------+-------------+------------+----------+
| .5 ton anvil   | Anvils R Us |       5.99 |       10 |
| 1 ton anvil    | Anvils R Us |       9.99 |        3 |
| TNT (5 sticks) | ACME        |      10.00 |        5 |
| Bird seed      | ACME        |      10.00 |        1 |
+----------------+-------------+------------+----------+
<-
```

