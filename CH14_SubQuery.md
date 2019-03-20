# 子查询

## 过滤
列出订购物品 TNT2 的所有客户：
1. 检索包含物品 TNT2 的所有订单的编号
2. 检索具有前一步骤列出的订单编号的所有客户的 ID
3. 检索前一步骤返回的所有客户 ID 的客户信息

```mysql
SELECT order_num
FROM orderitems
WHERE prod_id = 'TNT2';
->
+-----------+
| order_num |
+-----------+
|     20005 |
|     20007 |
+-----------+
<-

SELECT cust_id
FROM orders
WHERE order_num IN (20005, 20007);
->
+---------+
| cust_id |
+---------+
|   10001 |
|   10004 |
+---------+
<-

SELECT cust_name, cust_contact
FROM customers
WHERE cust_id IN (10001, 10004);
->
+----------------+--------------+
| cust_name      | cust_contact |
+----------------+--------------+
| Coyote Inc.    | Y Lee        |
| Yosemite Place | Y Sam        |
+----------------+--------------+
<-
```

等同于使用子查询：
```mysql
SELECT cust_name, cust_contact
FROM customers
WHERE cust_id IN (SELECT cust_id
                  FROM orders
                  WHERE order_num IN (SELECT order_num
                                      FROM orderitems
                                      WHERE prod_id = 'TNT2'));
```
- 子查询总是从内向外处理
- 子查询必须保证 SELECT 具有与 WHERE 中相同数目的列

## 作为计算字段使用子查询
1. 从 customers 表中检索客户列表
2. 对于检索除的每个客户，统计其在 orders 表中的订单数目
```mysql
SELECT cust_name,
       cust_state,
       (SELECT COUNT(*)
        FROM orders
        WHERE orders.cust_id = customers.cust_id) AS orders
FROM customers
ORDER BY cust_name;
->
+----------------+------------+--------+
| cust_name      | cust_state | orders |
+----------------+------------+--------+
| Coyote Inc.    | MI         |      2 |
| E Fudd         | IL         |      1 |
| Mouse House    | OH         |      0 |
| Wascals        | IN         |      1 |
| Yosemite Place | AZ         |      1 |
+----------------+------------+--------+
<-
```
任何时候只要列名可能有多义性，就必须使用**完全限定名**








