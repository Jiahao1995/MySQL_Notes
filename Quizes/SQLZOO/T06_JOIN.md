# Music Tutorial
1.
```mysql
SELECT title, artist
FROM album
JOIN track ON album.asin = track.album
WHERE song = 'Alison';
```

2.
```mysql
SELECT artist
FROM album
JOIN track ON album.asin = track.album
WHERE song = 'Exodus';
```

3.
```mysql
SELECT song
FROM track
JOIN album ON album.asin = track.album
WHERE title = 'Blur';
```

4.
```mysql
SELECT title, count(track.album)
FROM album
JOIN track ON album.asin = track.album
GROUP BY title;
```

5.
```mysql
SELECT title, count(song)
FROM album
JOIN track ON album.asin = track.album
WHERE song LIKE '%Heart%'
GROUP BY title;
```

6.
```mysql
SELECT song
FROM track
JOIN album ON album.asin = track.album
WHERE track.song = album.title;
```

7.
```mysql
SELECT title
FROM album
WHERE title = artist
GROUP BY title;
```

8.
```mysql

```

9.
```mysql

```

10.
```mysql
SELECT title, COUNT(song)
FROM album
JOIN track ON album.asin = track.album
GROUP BY title
ORDER BY COUNT(song) DESC, title;
```




