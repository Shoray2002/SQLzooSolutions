# SQLzooSolutions
The following are the solutions to the [SQLZOO Tutorial](http://sqlzoo.net/wiki/SQL_Tutorial). 


## Sections:
1. [SELECT-basics](#SELECT-basics)
2. [SELECT-names](#SELECT-names)
3. [SELECT-from-WORLD](#SELECT-from-WORLD)
4. [SELECT-from-NOBEL](#SELECT-from-nobel)
5. [SELECT-within-SELECT](#SELECT-within-SELECT)
<!-- 4. [SELECT in SELECT](#select-in-select) -->
<!-- 5. [SUM and COUNT](#sum-and-count) -->
<!-- 6. [JOIN](#join) -->
<!-- 7. [More JOIN](#more-join) -->
<!-- 8. [Using NULL](#using-null) -->
<!-- 9. [Self JOIN](#self-join) -->


## SELECT-basics

1.
```sql
  SELECT population FROM world
  WHERE name = 'Germany'
```
2.
```sql
    SELECT name, population FROM world
     WHERE name IN ('Sweden', 'Norway','Denmark');
```

3.
```sql
    SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
```
## SELECT names
1.
```sql
   SELECT name FROM world
  WHERE name LIKE 'Y%'
```

2.
```sql
SELECT name FROM world
  WHERE name LIKE '%y'
  ```
  
 3.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%x%'
```
  
 4.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%land'
```
  
 5.
 ```sql
   SELECT name FROM world
  WHERE name LIKE 'C%%ia'
```
  
 6.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%oo%'
```
  
 7.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%a%a%a%'
```
  
 8.
 ```sql
   SELECT name FROM world
 WHERE name LIKE '_t%'
ORDER BY name
```
  
 9.
 ```sql
   SELECT name FROM world
 WHERE name LIKE '%o__o%'
```
  
 10.
 ```sql
   SELECT name FROM world
 WHERE length(name)=4
```
  
   (Harder Questions)
   
 11.
 ```sql
   SELECT name
  FROM world
 WHERE name=capital
```
  
 12.
 ```sql
   SELECT name
  FROM world
 WHERE capital=concat(name, ' City')

```
  
 13.
 ```sql
   SELECT capital,name  FROM world WHERE capital LIKE concat('%',name,'%')
```
  
 14.
 ```sql
   SELECT capital,name  FROM world WHERE capital LIKE concat('%',name,'%') and length(capital)>length(name)
```
  
 15.
 ```sql
   SELECT name, REPLACE( capital, name, '') as 'ext'
FROM world
WHERE capital LIKE concat('%',name,'%') and length(capital)>length(name)
```
## SELECT from WORLD

  
 1.
 ```sql
   SELECT name, continent, population FROM world
```
  
 2.
 ```sql
   SELECT name FROM world
WHERE population >= 200000000
```
  
 3.
 ```sql
   SELECT name, gdp/population FROM world WHERE population >= 200000000
```
  
 4.
 ```sql
   SELECT name, population/1000000 FROM world WHERE continent = 'South America'
```

5.
 ```sql
   SELECT name, population FROM world WHERE name IN ('Germany', 'France', 'Italy');
```
6.
 ```sql
  SELECT name FROM world WHERE name LIKE '%United%'
```
7.
 ```sql
   SELECT name, population, area FROM world WHERE area>3000000 OR population>250000000
```
8.
 ```sql
   SELECT name, population, area FROM world WHERE area>3000000 XOR population>250000000
```
9.
 ```sql
   SELECT name, ROUND(population/1000000,2),ROUND(gdp/1000000000,2) area FROM world WHERE continent='South America'
```
10.
 ```sql
   SELECT name, ROUND(gdp/population,-3) FROM world WHERE gdp>1000000000000
```
11.
 ```sql
   SELECT name, capital
  FROM world
 WHERE LENGTH(name)=LENGTH(capital)
```
12.
 ```sql
  SELECT name, capital
FROM world WHERE LEFT(name,1)=LEFT(capital,1) AND name<>capital
```
13.
 ```sql
   SELECT name
   FROM world
WHERE name LIKE '%a%' AND name LIKE '%e%' AND name LIKE '%i%' AND name LIKE '%o%' AND name LIKE '%u%'
  AND name NOT LIKE '% %'
```

## SELECT-from-nobel

1.
 ```sql
   SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
```

2.
 ```sql
   SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
```
3.
 ```sql
   SELECT yr,subject 
  FROM nobel
WHERE winner='Albert Einstein' 
```
4.
 ```sql
   SELECT winner
  FROM nobel
 WHERE yr >= 2000
   AND subject = 'Peace'
```
5.
 ```sql
  SELECT yr, subject, winner
  FROM nobel
 WHERE yr>=1980 AND yr <= 1989  AND subject = 'Literature'
```
6.
 ```sql
   SELECT * FROM nobel
 WHERE winner IN ('Theodore Roosevelt',
                  'Woodrow Wilson',
                  'Jimmy Carter','Barack Obama')
```
7.
 ```sql
   SELECT winner
  FROM nobel
 WHERE winner LIKE 'John%'
```
8.
 ```sql
   SELECT yr, subject, winner
  FROM nobel
 WHERE (yr=1980 AND subject = 'Physics') OR (yr=1984 AND subject = 'Chemistry')
```
9.
 ```sql
   SELECT yr, subject, winner
  FROM nobel
 WHERE yr=1980 AND  subject <> 'Medicine' AND subject <> 'Chemistry'
```

10.
 ```sql
   SELECT yr, subject, winner
  FROM nobel
 WHERE (yr<1910 AND  subject='Medicine') OR (yr>=2004 AND subject='Literature')
```
11.
 ```sql
   SELECT *
  FROM nobel
 WHERE winner ='Peter Grünberg'
```
12.
 ```sql
   SELECT *
  FROM nobel
 WHERE winner = "Eugene O'Neill"
```
13.
 ```sql
  SELECT winner, yr, subject
FROM nobel 
WHERE winner LIKE 'Sir%'
ORDER BY yr DESC, winner

```
14.
 ```sql
   select winner, subject
from nobel
where yr=1984 
order by subject in ('Physics','Chemistry'),subject,winner
```

## SELECT-within-SELECT
