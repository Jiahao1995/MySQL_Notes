# 插入数据

## 数据插入

## 插入完整的行
```mysql
INSERT INTO Customers
VALUES(NULL,
	   'Pep E. LaPew',
	   '100 Main Street',
	   'Los Angeles',
	   'CA',
	   '90046',
	   'USA',
	   NULL,
	   NULL);
->
Query OK, 1 row affected (0.01 sec)
<-
```
更保险的方法：
```mysql
INSERT INTO customers(cust_name,
					  cust_address,
					  cust_city,
					  cust_state,
					  cust_zip,
					  cust_country,
					  cust_contact,
					  cust_email)

VALUES(NULL,
	   'Pep E. LaPew',
	   '100 Main Street',
	   'Los Angeles',
	   'CA',
	   '90046',
	   'USA',
	   NULL,
	   NULL);
```
这种方法也可以不按照次序填写，但必须一一对应

## 插入多个行
```mysql
INSERT INTO customers(cust_name,
					  cust_address,
					  cust_city,
					  cust_state,
					  cust_zip,
					  cust_country)
VALUES('Pep E. LaPew',
	   '100 Main Street',
	   'Los Angeles',
	   'CA',
	   '90046',
	   'USA'),
	  ('M. Martian',
 	   '42 Galaxy Way',
 	   'New York',
 	   'NY',
 	   '11213',
 	   'USA');
```

## 插入检索出的数据
```mysql
INSERT INTO customers(cust_id,
					  cust_contact,
					  cust_email,
					  cust_name,
					  cust_address,
					  cust_city,
					  cust_state,
					  cust_zip,
					  cust_country)
SELECT cust_id,
	   cust_contact,
	   cust_email,
	   cust_name,
	   cust_address,
	   cust_city,
	   cust_state,
	   cust_zip,
	   cust_country
FROM custnew;
```







