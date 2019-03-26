1.
```mysql
SELECT id, title
FROM movie
WHERE yr = 1962;
```


2.
```mysql
SELECT yr
FROM movie
WHERE title = 'Citizen Kane';
```

3.
```mysql
SELECT id, title, yr
FROM movie
WHERE title LIKE '%Star Trek%';
```

4.
```mysql
SELECT id
FROM actor
WHERE name = 'Glenn Close';
```

5.
```mysql
SELECT id
FROM movie
WHERE title = 'Casablanca';
```

6.
```mysql
SELECT name
FROM actor
JOIN casting ON actor.id = casting.actorid
WHERE movieid = 11768;
```

7.
```mysql
SELECT name
FROM actor
JOIN casting ON casting.actorid = actor.id
WHERE movieid = (
	SELECT id
	FROM movie
	WHERE title = 'Alien');
```

8.
```mysql
SELECT title
FROM movie
JOIN casting ON casting.movieid = movie.id
WHERE actorid = (
	SELECT id
	FROM actor
	WHERE name = 'Harrison Ford');
```

9.
```mysql
SELECT title
FROM movie
JOIN casting ON casting.movieid = movie.id
WHERE actorid = (
	SELECT id
	FROM actor
	WHERE name = 'Harrison Ford')
AND ord != 1;
```


10.
```mysql
SELECT title, name
FROM casting
JOIN movie ON casting.movieid = movie.id
JOIN actor ON casting.actorid = actor.id
WHERE yr = 1962 AND ord = 1;
```

11.
```mysql
SELECT yr, COUNT(title)
FROM casting
JOIN movie ON casting.movieid = movie.id
JOIN actor ON casting.actorid = actor.id
WHERE name = 'John Travolta'
GROUP BY yr
HAVING COUNT(title) > 2;
```

12.
```mysql
SELECT title, name
FROM casting
JOIN movie ON casting.movieid = movie.id
JOIN actor ON casting.actorid = actor.id
WHERE movieid IN (
	SELECT movieid
	FROM casting
	WHERE actorid = (
		SELECT id
		FROM actor
		WHERE name = 'Julie Andrews'))
AND ord = 1;
```

13.
```mysql
SELECT name
FROM actor
JOIN casting ON actorid = id
WHERE (
	SELECT COUNT(ord)
	FROM casting
	WHERE actorid = id AND ord = 1) >= 30
GROUP BY name;
```

14.
```mysql
SELECT title, COUNT(actorid)
FROM movie
JOIN casting ON movieid = id
WHERE yr = 1978
GROUP BY title
ORDER BY COUNT(actorid) DESC, title;
```

15.
```mysql
SELECT DISTINCT name
FROM actor
JOIN casting ON actorid = id
WHERE movieid IN (
	SELECT movieid
	FROM casting
	JOIN actor ON actorid = id
	WHERE name = 'Art Garfunkel') AND name <> 'Art Garfunkel';
```






