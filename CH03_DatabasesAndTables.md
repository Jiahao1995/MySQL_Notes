# Databases and Tables

## 显示数据库
```mysql
SHOW DATABASES;
->
+--------------------+
| Database           |
+--------------------+
| information_schema |
| crashcourse        |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
<-
```

## 选择数据库
```mysql
USE crashcourse;
->
Database changed
<-
```

## 显示列表
```mysql
SHOW TABLES;
->
+-----------------------+
| Tables_in_crashcourse |
+-----------------------+
| customers             |
| orderitems            |
| orders                |
| productnotes          |
| products              |
| vendors               |
+-----------------------+
<-
```

## 显示表列
```mysql
SHOW COLUMNS FROM customers;
->
+--------------+-----------+------+-----+---------+----------------+
| Field        | Type      | Null | Key | Default | Extra          |
+--------------+-----------+------+-----+---------+----------------+
| cust_id      | int(11)   | NO   | PRI | NULL    | auto_increment |
| cust_name    | char(50)  | NO   |     | NULL    |                |
| cust_address | char(50)  | YES  |     | NULL    |                |
| cust_city    | char(50)  | YES  |     | NULL    |                |
| cust_state   | char(5)   | YES  |     | NULL    |                |
| cust_zip     | char(10)  | YES  |     | NULL    |                |
| cust_country | char(50)  | YES  |     | NULL    |                |
| cust_contact | char(50)  | YES  |     | NULL    |                |
| cust_email   | char(255) | YES  |     | NULL    |                |
+--------------+-----------+------+-----+---------+----------------+
<-
```
- Field 字段名
- Type 数据类型
- Null 是否允许 null
- Key 键信息
- Default 默认值
- Extra 其他信息
  - auto_increment 自动增量，当添加新的行时，编号自动加一

## 其他 SHOW 语句
- SHOW STATUS 用于显示广泛的服务器状态信息
- SHOW CREATE DATABASE 显示创建特定数据库
- SHOW CREATE TABLE 显示创建特定列表
- SHOW GRANTS 显示授予用户的安全权限
- SHOW ERRORS 显示服务器错误
- SHOW WARNINGS 显示服务器警告消息
