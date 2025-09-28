# Employee Salaries

 **Write a query that prints a list of employee names (i.e.: the _name_ attribute) for employees in Employee having a salary greater than  per month who have been employees for less than  months. Sort your result by ascending _employee_id_.**
**Input Format**
**The Employee table containing employee data for a company is described as follows:**

**![](https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png)**
**where _employee_id_ is an employee's ID number, _name_ is their name, _months_ is the total number of months they've been working for the company, and _salary_ is the their monthly salary.**
**Sample Input**
**![](https://s3.amazonaws.com/hr-challenge-images/19630/1458558612-af3da3ceb7-ScreenShot2016-03-21at4.32.59PM.png)**
**Sample Output**
```
Angela
Michael
Todd
Joe
```

**Explanation**

**_Angela_ has been an employee for  month and earns  per month.**

**_Michael_ has been an employee for  months and earns  per month.**

**_Todd_ has been an employee for  months and earns  per month.**

**_Joe_ has been an employee for  months and earns  per month.**

**We order our output by ascending _employee_id_.**

**SOLUTION :**
```SQL
SET NOCOUNT ON;

SELECT
    NAME

FROM
    Employee

WHERE
     SALARY > 2000 AND MONTHS < 10

ORDER BY
      employee_id ASC;
go
```


# Revising the Select Query I

**Query all columns for all American cities in the CITY table with populations larger than `100000`. The CountryCode for America is `USA`.**

**The CITY table is described as follows:**

**![CITY.jpg](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)**

**SOLUTION:**
```SQL
SET NOCOUNT ON;

SELECT *

FROM
   CITY
   
WHERE
   population > 100000 AND CountryCode ='USA';
go
```

# Weather Observation Station 5

**Query the two cities in STATION with the shortest and longest _CITY_ names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.**  
**The STATION table is described as follows:**
**![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg "Station.jpg")**
**where LAT_N is the northern latitude and LONG_W is the western longitude.**

**Sample Input**
**For example, CITY has four entries: DEF, ABC, PQRS and WXY.**

**Sample Output**
```
ABC 3
PQRS 4
```
**Explanation**
**When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths  and . The longest name is PQRS, but there are  options for shortest named city. Choose ABC, because it comes first alphabetically.**

**Note**  
**You can write two separate queries to get the desired output. It need not be a single query.**

**Solution :** 
```sql 
SET NOCOUNT ON;

select distinct top 1 city,len(city)
from STATION
ORDER BY LEN(CITY) ASC, CITY ASC

select distinct top 1 city,len(city)
from STATION
order by LEN(CITY) DESC, CITY DESC;

go
```


# Weather Observation Station 6


**Query the list of _CITY_ names starting with vowels (i.e., `a`, `e`, `i`, `o`, or `u`) from STATION. Your result _cannot_ contain duplicates.**

```SQL
SET NOCOUNT ON;

select DISTINCT CITY

FROM
   STATION
   
WHERE
   CITY LIKE '[aeiou]%';

  

go
```

#  Weather Observation Station 7

**Query the list of _CITY_ names ending with vowels (a, e, i, o, u) from STATION. Your result _cannot_ contain duplicates.**

```SQL
SET NOCOUNT ON;

select distinct city

from 
      STATION

where city like '%[aeiou]';

go
```
# Weather Observation Station 8

**Query the list of _CITY_ names from STATION which have vowels (i.e., _a_, _e_, _i_, _o_, and _u_) as both their first _and_ last characters. Your result cannot contain duplicates.**

```SQL
SET NOCOUNT ON;
  
select distinct city

from
      STATION
where city like '[aeiou]%' and city like '%[aeiou]' ;
go

```
#  Weather Observation Station 9

**Query the list of _CITY_ names not starting with vowels (i.e., `a`, `e`, `i`, `o`, or `u`) from STATION. Your result _cannot_ contain duplicates.**

```SQL
SET NOCOUNT ON;
select distinct city
from
      STATION
where city like '[^aeiou]%';
go

-- OR 

select distinct city

from
 STATION
 
where city not like '[aeiou]%';
```

# Weather Observation Station 10
**Query the list of _CITY_ names from STATION that _do not end_ with vowels. Your result cannot contain duplicates.**

```SQL

SET NOCOUNT ON;
select distinct city
from
      STATION
where city like '%[^aeiou]';
go

-- OR 

select distinct city

from
 STATION
 
where city not like '%[aeiou]';
```
# Weather Observation Station 11

**Query the list of _CITY_ names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.**

```SQL

SET NOCOUNT ON;
select distinct city
from
      STATION
where city like '%[^aeiou]' and city like '[^aeiou]%' ;
go

-- OR 

select distinct city

from
 STATION
 
where city not like '%[aeiou]'and city like '[aeiou]%' ;
```
# Higher Than 75 Marks

**Query the _Name_ of any student in STUDENTS who scored higher than  _Marks_. Order your output by the _last three characters_ of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending _ID_.**

**Input Format**

**The STUDENTS table is described as follows:**
**![[Pasted image 20250918092039.png]]**

**The _Name_ column only contains uppercase (`A`-`Z`) and lowercase (`a`-`z`) letters.**

**Sample Input**
**![[Pasted image 20250918092047.png]]**
**Sample Output**

```
Ashley
Julia
Belvet
```

**Explanation**

**Only Ashley, Julia, and Belvet have _Marks_ > . If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.**


```SQL
SET NOCOUNT ON;

select
  name

from
   STUDENTS

where
   marks > 75

order by

   RIGHT(name,3),ID;
go
```
#





# 



```sql
```



```SQL
```
#


```SQL
```

#

```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#


```SQL
```
#


```SQL
```
#


```SQL
```
#

```SQL
```
#
```SQL
```
#

```SQL
```
#

```SQL
```
#


```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#

```SQL
```
#
```SQL
```


#
```SQL
```
#
```SQL
```
#
```SQL
```

#
```SQL
```
#
