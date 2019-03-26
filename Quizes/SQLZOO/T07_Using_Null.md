# Teachers in Departments
1.
```mysql
SELECT name
FROM teacher
WHERE dept IS NULL;
```

2.
```mysql
SELECT teacher.name, dept.name
FROM teacher
JOIN dept ON teacher.dept = dept.id;
```

3.
```mysql
SELECT teacher.name, dept.name
FROM teacher
LEFT JOIN dept ON teacher.dept = dept.id;
```

4.
```mysql
SELECT teacher.name, dept.name
FROM teacher
RIGHT JOIN dept ON teacher.dept = dept.id;
```

5.
```mysql
SELECT name, COALESCE(mobile, '07986 444 2266')
FROM teacher;
```

6.
```mysql
SELECT teacher.name, COALESCE(dept.name, 'None')
FROM teacher
LEFT JOIN dept ON teacher.dept = dept.id;
```

7.
```mysql
SELECT COUNT(name), COUNT(mobile)
FROM teacher;
```

8.
```mysql
SELECT dept.name, COUNT(teacher.name)
FROM teacher
RIGHT JOIN dept ON teacher.dept = dept.id
GROUP BY dept.name;
```

9.
```mysql
SELECT name,
CASE WHEN dept in (1, 2) THEN 'Sci'
ELSE 'Art' END
FROM teacher;
```

10.
```mysql
SELECT name,
CASE WHEN dept in (1, 2) THEN 'Sci'
WHEN dept = 3 THEN 'Art'
ELSE 'None' END
FROM teacher;
```

# Scottish Parliament
1.
```mysql
SELECT name
FROM msp
WHERE party IS NULL;
```

2.
```mysql
SELECT name, leader
FROM party;
```

3.
```mysql
SELECT name, leader
FROM party
WHERE leader IS NOT NULL;
```

4.
```mysql
SELECT party.name
FROM msp 
JOIN party ON msp.party = party.code
GROUP BY party.name;
```

5.
```mysql
SELECT msp.name, party.name
FROM msp
LEFT JOIN party ON msp.party = party.code
ORDER BY msp.name;
```

6.
```mysql
SELECT party.name, COUNT(msp.name)
FROM party
JOIN msp ON msp.party = party.code
GROUP BY party.name;
```

7.
```mysql
SELECT party.name, COUNT(msp.name)
FROM party
LEFT JOIN msp ON msp.party = party.code
GROUP BY party.name;
```




