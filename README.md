# SQLzooSolutions
The following are the solutions to the [SQLZOO Tutorial](http://sqlzoo.net/wiki/SQL_Tutorial). 


## Sections:
1. [SELECT-basics](#SELECT-basics)
2. [SELECT-names](#SELECT-names)
3. [SELECT-from-WORLD](#SELECT-from-WORLD)
<!-- 3. [SELECT from NOBEL](#select-from-nobel) -->
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

  <!-- 
 16.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%x%'
```
  
 17.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%x%'
```
  
 18.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%x%'
```
  
 19.
 ```sql
   SELECT name FROM world
  WHERE name LIKE '%x%'
```
 -->
