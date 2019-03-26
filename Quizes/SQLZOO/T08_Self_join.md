1.
```mysql
SELECT COUNT(name)
FROM stops;
```

2.
```mysql
SELECT id
FROM stops
WHERE name = 'Craiglockhart';
```

3.
```mysql
SELECT id, name
FROM stops
JOIN route on stops.id = route.stop
WHERE num = 4 AND company = 'LRT';
```

4.
```mysql
SELECT company, num, COUNT(*)
FROM route
WHERE stop = 149 OR stop = 53
GROUP BY company, num
HAVING COUNT(*) = 2;
```

5.
```mysql

```












