1.
```mysql
SELECT SUM(population)
FROM world;
```

2.
```mysql
SELECT DISTINCT continent
FROM world;
```

3.
```mysql
SELECT SUM(gdp)
FROM world
WHERE continent = 'Africa';
```

4.
```mysql
SELECT COUNT(name)
FROM world
WHERE area >= 1000000;
```

5.
```mysql
SELECT SUM(population)
FROM world
WHERE name IN ('Estonia', 'Latvia', 'Lithuania');
```

6.
```mysql
SELECT continent, COUNT(name)
FROM world
GROUP BY continent;
```

7.
```mysql
SELECT continent, COUNT(name)
FROM world
WHERE population >= 10000000
GROUP BY continent;
```

8.
```mysql
SELECT continent
FROM world
GROUP BY continent
HAVING SUM(population) >= 10000000;
```













