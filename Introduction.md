# 导入示例数据库 crashcourse
1. 下载文件 mysql_scripts，解压缩
2. 打开 Termial，输入 mysql -uroot -p 进入 MySQL
3. 输入 CREATE database crashcourse;
4. 输入 USE crashcourse;
5. 输入 SOURCE /Users/lijiahao/Downloads/mysql_scripts(自行替换路径)/create.sql;
6. 输入 SOURCE /Users/lijiahao/Downloads/mysql_scripts(自行替换路径)/populate.sql;
7. 输入 SHOW databases; 出现 crashcourse，导入成功
