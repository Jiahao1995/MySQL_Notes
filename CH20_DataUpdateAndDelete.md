# 更新和删除数据

## 更新数据
```mysql
UPDATE customers
SET cust_email = 'elmer@fudd.com'
WHERE cust_id = 10005;
```
UPDATE 语句必须以 WHERE 子句结束，否则将应用于所有的行


更新多个列只需要使用单个 SET 命令：
```mysql
UPDATE customers
SET cust_name = 'The Fudds',
	cust_email = 'elmer@fudd.com'
WHERE cust_id = 10005;
```

可以将某个值设置为 NULL 来删除它：
```mysql
UPDATE customers
SET cust_email = NULL
WHERE cust_id = 10005;
```

## 删除数据
```mysql
DELETE FROM customers
WHERE cust_id = 10006;
```
DELETE 删除整行而不是删除列

如果想删除所有的行，使用 TRUNCATE TABLE 语句，性能更好

## 更新和删除的指导原则
- UPDATE 和 DELETE 都必须带 WHERE 子句
- 保证每个表都有主键
- 使用前，先用 SELECT 进行测试，保证其过滤的是正确的记录





