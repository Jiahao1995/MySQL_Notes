1.
```mysql
SELECT name
FROM world
WHERE name LIKE 'Y%';
```

2.
```mysql
SELECT name
FROM world
WHERE name LIKE '%y';
```

3.
```mysql
SELECT name
FROM world
WHERE name LIKE '%x%';
```

4.
```mysql
SELECT name
FROM world
WHERE name LIKE '%land';
```

5.
```mysql
SELECT name
FROM world
WHERE name LIKE 'C%ia';
```

6.
```mysql
SELECT name
FROM world
WHERE name LIKE '%oo%';
```

7.
```mysql
SELECT name
FROM world
WHERE name LIKE '%a%a%a%';
```

8.
```mysql
SELECT name
FROM world
WHERE name LIKE '_t%'
ORDER BY name;
```

9.
```mysql
SELECT name
FROM world
WHERE name LIKE '%o__o%';
```

10.
```mysql
SELECT name
FROM world
WHERE name LIKE '____';
```

11.
```mysql
SELECT name
FROM world
WHERE name = capital;
```

12.
```mysql
SELECT name
FROM world
WHERE capital = concat(name, 'City');
```

13.
```mysql
SELECT capital, name
FROM world
WHERE capital LIKE CONCAT('%', name, '%');
```

14.
```mysql
SELECT capital, name
FROM world
WHERE capital LIKE CONCAT(name, '%') AND (capital != name);
```

15.
```mysql
SELECT name, replace(capital, name, '')
FROM world
WHERE capital LIKE CONCAT(name, '%') AND (capital != name);
```






