```mysql
-- 创建数据库 school
CREATE DATABASE school;

USE school;

-- 创建学生表 Student
CREATE TABLE Student(
s_id VARCHAR(20),
s_name VARCHAR(20) NOT NULL DEFAULT '',
s_birth VARCHAR(20) NOT NULL DEFAULT '',
s_sex VARCHAR(10) NOT NULL DEFAULT '',
PRIMARY KEY(s_id)
);

-- 创建课程表 Course
CREATE TABLE Course(
c_id VARCHAR(20),
c_name VARCHAR(20) NOT NULL DEFAULT '',
t_id VARCHAR(20) NOT NULL,
PRIMARY KEY(c_id)
);

-- 创建教师表 Teacher
CREATE TABLE Teacher(
t_id VARCHAR(20),
t_name VARCHAR(20) NOT NULL DEFAULT '',
PRIMARY KEY(t_id)
);

-- 创建成绩表 'Score'
CREATE TABLE `Score`(
s_id VARCHAR(20),
c_id VARCHAR(20),
s_score INT(3),
PRIMARY KEY(s_id,c_id)
);

-- 插入数据
-- 插入学生表测试数据
insert into Student values('01' , 'ZhaoLei' , '1990-01-01' , 'M');
insert into Student values('02' , 'QianDian' , '1990-12-21' , 'M');
insert into Student values('03' , 'SunFeng' , '1990-05-20' , 'M');
insert into Student values('04' , 'LiYun' , '1990-08-06' , 'M');
insert into Student values('05' , 'ZhouMei' , '1991-12-01' , 'F');
insert into Student values('06' , 'WuLan' , '1992-03-01' , 'F');
insert into Student values('07' , 'ZhenZhu' , '1989-07-01' , 'F');
insert into Student values('08' , 'WangJu' , '1990-01-20' , 'F');

-- 课程表测试数据
insert into Course values('01' , 'Chinese' , '02');
insert into Course values('02' , 'Math' , '01');
insert into Course values('03' , 'English' , '03');

-- 教师表测试数据
insert into Teacher values('01' , 'ZhangSan');
insert into Teacher values('02' , 'LiSi');
insert into Teacher values('03' , 'WangWu');

-- 成绩表测试数据
insert into Score values('01' , '01' , 80);
insert into Score values('01' , '02' , 90);
insert into Score values('01' , '03' , 99);
insert into Score values('02' , '01' , 70);
insert into Score values('02' , '02' , 60);
insert into Score values('02' , '03' , 80);
insert into Score values('03' , '01' , 80);
insert into Score values('03' , '02' , 80);
insert into Score values('03' , '03' , 80);
insert into Score values('04' , '01' , 50);
insert into Score values('04' , '02' , 30);
insert into Score values('04' , '03' , 20);
insert into Score values('05' , '01' , 76);
insert into Score values('05' , '02' , 87);
insert into Score values('06' , '01' , 31);
insert into Score values('06' , '03' , 34);
insert into Score values('07' , '02' , 89);
insert into Score values('07' , '03' , 98);
```

```mysql
-- tables in school
+------------------+
| Tables_in_school |
+------------------+
| Course           |
| Score            |
| Student          |
| Teacher          |
+------------------+

-- Course
+------+---------+------+
| c_id | c_name  | t_id |
+------+---------+------+
| 01   | Chinese | 02   |
| 02   | Math    | 01   |
| 03   | English | 03   |
+------+---------+------+

-- Score
+------+------+---------+
| s_id | c_id | s_score |
+------+------+---------+
| 01   | 01   |      80 |
| 01   | 02   |      90 |
| 01   | 03   |      99 |
| 02   | 01   |      70 |
| 02   | 02   |      60 |
| 02   | 03   |      80 |
| 03   | 01   |      80 |
| 03   | 02   |      80 |
| 03   | 03   |      80 |
| 04   | 01   |      50 |
| 04   | 02   |      30 |
| 04   | 03   |      20 |
| 05   | 01   |      76 |
| 05   | 02   |      87 |
| 06   | 01   |      31 |
| 06   | 03   |      34 |
| 07   | 02   |      89 |
| 07   | 03   |      98 |
+------+------+---------+

-- Student
+------+----------+------------+-------+
| s_id | s_name   | s_birth    | s_sex |
+------+----------+------------+-------+
| 01   | ZhaoLei  | 1990-01-01 | M     |
| 02   | QianDian | 1990-12-21 | M     |
| 03   | SunFeng  | 1990-05-20 | M     |
| 04   | LiYun    | 1990-08-06 | M     |
| 05   | ZhouMei  | 1991-12-01 | F     |
| 06   | WuLan    | 1992-03-01 | F     |
| 07   | ZhenZhu  | 1989-07-01 | F     |
| 08   | WangJu   | 1990-01-20 | F     |
+------+----------+------------+-------+

-- Teacher
+------+----------+
| t_id | t_name   |
+------+----------+
| 01   | ZhangSan |
| 02   | LiSi     |
| 03   | WangWu   |
+------+----------+
```



