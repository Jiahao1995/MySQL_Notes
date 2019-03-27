1.
```mysql
SELECT A_STRONGLY_AGREE
FROM nss
WHERE question = 'Q01'
AND institution = 'Edinburgh Napier University'
AND subject = '(8) Computer Science';
```

2.
```mysql
SELECT institution, subject
FROM nss
WHERE score >= 100 AND question = 'Q15';
```

3.
```mysql
SELECT institution, score
FROM nss
WHERE subject = '(8) Computer Science'
AND score < 50
AND question = 'Q15';
```

4.
```mysql
SELECT subject, SUM(response)
FROM nss
WHERE question = 'Q22'
AND subject IN ('(8) Computer Science', '(H) Creative Arts and Design')
GROUP BY subject;
```

5.
```mysql
SELECT subject, SUM(A_STRONGLY_AGREE * response / 100)
FROM nss
WHERE question = 'Q22'
AND subject IN ('(8) Computer Science', '(H) Creative Arts and Design')
GROUP BY subject;
```

6.
```mysql
SELECT subject, round(SUM(A_STRONGLY_AGREE * response / 100) / SUM(response) * 100, 0)
FROM nss
WHERE question = 'Q22'
AND subject IN ('(8) Computer Science', '(H) Creative Arts and Design')
GROUP BY subject;
```

7.
```mysql
SELECT institution, round(SUM(score * response) / SUM(response), 0)
FROM nss
WHERE question = 'Q22'
AND institution LIKE '%Manchester%'
GROUP BY institution
ORDER BY institution
```








