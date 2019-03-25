1.
```mysql
SELECT name
FROM world
WHERE population > (
	SELECT population
	FROM world
	WHERE name = 'Russia');
```

2.
```mysql
SELECT name
FROM world
WHERE gdp > (
	SELECT gdp
	FROM world
	WHERE name = 'United Kingdom');
```

3.
```mysql
SELECT name, continent
FROM world
WHERE continent IN (
	SELECT continent
	FROM world
	WHERE name IN ('Argentina', 'Australia'))
ORDER BY name;
```

4. 
```mysql
SELECT name, population
FROM world
WHERE population > (
	SELECT population
	FROM world
	WHERE name = 'Canada') 
AND population < (
	SELECT population
	FROM world
	WHERE name = 'Poland');
```

5.
```mysql
SELECT name, CONCAT(ROUND((population/(
	SELECT population
	FROM world
	WHERE name = 'Germany') * 100), 0), '%')
FROM world
WHERE continent = 'Europe';
```

6.
```mysql
SELECT name 
FROM world
WHERE gdp > all (
	SELECT gdp
	FROM world
	WHERE continent = 'Europe' AND gdp > 0);
```

7.
```mysql
SELECT continent, name, area
FROM world x
WHERE area >= ALL (
	SELECT area
	FROM world y
	WHERE x.continent = y.continent AND area > 0);
```

8.
```mysql
SELECT continent, name
FROM world x
WHERE x.name = (
	SELECT y.name
	FROM world y
	WHERE y.continent = x.continent
	ORDER BY name
	LIMIT 1);
```

9.
```mysql
SELECT name, continent, population
FROM world x
WHERE 25000000 >= ALL (
	SELECT y.population
	FROM world y
	WHERE y.continent = x.continent);
```

10.
```mysql
SELECT name, continent
FROM world x
WHERE x.population/3 > ALL (
	SELECT y.population
	FROM world y
	WHERE x.continent = y.continent AND x.name != y.name AND y.population > 0);
```








