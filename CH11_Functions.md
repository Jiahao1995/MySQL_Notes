# 数据处理函数

## 使用函数

### 文本处理函数
```mysql
SELECT vend_name, Upper(vend_name) AS vend_name_upcase
FROM vendors
ORDER BY vend_name;
->
+----------------+------------------+
| vend_name      | vend_name_upcase |
+----------------+------------------+
| ACME           | ACME             |
| Anvils R Us    | ANVILS R US      |
| Furball Inc.   | FURBALL INC.     |
| Jet Set        | JET SET          |
| Jouets Et Ours | JOUETS ET OURS   |
| LT Supplies    | LT SUPPLIES      |
+----------------+------------------+
<-
```
- Left() 返回串左边的字符
- Length() 返回串的长度
- Locate() 找出串的一个子串
- Lower() 将串转换为小写
- LTrim() 去掉串左边的空格
- Right() 返回串右边的字符
- RTrim() 去掉串右边的空格
- Soundex() 返回串的 SOUNDEX 值
- SubString() 返回字串的字符
- Upper() 将串转换为大写

### 日期和时间处理函数
```mysql
SELECT cust_id, order_num, order_date
FROM orders
WHERE order_date = '2005-09-01';
->
+---------+-----------+---------------------+
| cust_id | order_num | order_date          |
+---------+-----------+---------------------+
|   10001 |     20005 | 2005-09-01 00:00:00 |
+---------+-----------+---------------------+
<-
```

- AddDate()
- AddTime()
- CurDate()
- CurTime()
- Date()
- DateDiff() 计算两个日期之差
- Date_Add() 高度灵活的日期运算函数
- Date_Format() 返回格式化的日期或时间串
- Day()
- DayOfWeek()
- Hour()
- Minute()
- Month()
- Now()
- Second()
- Time()
- Year()

#### 选择时间区间
```mysql
SELECT cust_id, order_num, order_date
FROM orders
WHERE Date(order_date) BETWEEN '2005-09-01' AND '2005-09-30';
->
+---------+-----------+---------------------+
| cust_id | order_num | order_date          |
+---------+-----------+---------------------+
|   10001 |     20005 | 2005-09-01 00:00:00 |
|   10003 |     20006 | 2005-09-12 00:00:00 |
|   10004 |     20007 | 2005-09-30 00:00:00 |
+---------+-----------+---------------------+
<-

SELECT cust_id, order_num, order_date
FROM orders
WHERE Year(order_date) = 2005 AND Month(order_date) = 9;
->
+---------+-----------+---------------------+
| cust_id | order_num | order_date          |
+---------+-----------+---------------------+
|   10001 |     20005 | 2005-09-01 00:00:00 |
|   10003 |     20006 | 2005-09-12 00:00:00 |
|   10004 |     20007 | 2005-09-30 00:00:00 |
+---------+-----------+---------------------+
<-
```

### 数值处理函数
- Abs()
- Cos()
- Exp()
- Mod()
- Pi()
- Rand()
- Sin()
- Sqrt()
- Tan()
