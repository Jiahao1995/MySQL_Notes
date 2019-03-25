1.
```mysql
SELECT population
FROM world
WHERE name = 'Germany';
```

2.
```mysql
SELECT name, population
FROM world
WHERE name IN ('Sweden', 'Norway', 'Denmark');
```

3.
```mysql
SELECT name, area
FROM world
WHERE area BETWEEN 200000 AND 250000;
```