###Revising the Select Query-1

Query all columns for all American cities in CITY with populations larger than 100,000. The CountryCode for America is USA.

The CITY table is described as follows:

|Field 	      | Type          |
|------------ |---------------|
|ID 	        |  NUMBER       |
|NAME 	      | VARCHAR2(17)  |
|COUNTRY CODE |  	VARCHAR2(3) |
|DISTRICT 	  |  VARCHAR2(20) |
|POPULATION 	| NUMBER        |

**Solution**
```sql
SELECT * FROM city WHERE population > 100000 AND countrycode="USA";
```

###Revising the Select Query-2

Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA. 

The CITY table is described as follows:

|Field 	      | Type          |
|------------ |---------------|
|ID 	        |  NUMBER       |
|NAME 	      | VARCHAR2(17)  |
|COUNTRY CODE |  	VARCHAR2(3) |
|DISTRICT 	  |  VARCHAR2(20) |
|POPULATION 	| NUMBER        |

**Solution**
```sql
SELECT name FROM city WHERE countrycode='USA' AND population > 120000 ;
```

###Select All

Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

|Field 	      | Type          |
|------------ |---------------|
|ID 	        |  NUMBER       |
|NAME 	      | VARCHAR2(17)  |
|COUNTRY CODE |  	VARCHAR2(3) |
|DISTRICT 	  |  VARCHAR2(20) |
|POPULATION 	| NUMBER        |

**Solution**
```sql
SELECT * FROM city;
```

###Select By ID

Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

|Field 	      | Type          |
|------------ |---------------|
|ID 	        |  NUMBER       |
|NAME 	      | VARCHAR2(17)  |
|COUNTRY CODE |  	VARCHAR2(3) |
|DISTRICT 	  |  VARCHAR2(20) |
|POPULATION 	| NUMBER        |

**Solution**
```sql
SELECT * FROM city WHERE id=1661;
```

###Japanese Cities' Attributes

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN. 

The CITY table is described as follows:

|Field 	      | Type          |
|------------ |---------------|
|ID 	        |  NUMBER       |
|NAME 	      | VARCHAR2(17)  |
|COUNTRY CODE |  	VARCHAR2(3) |
|DISTRICT 	  |  VARCHAR2(20) |
|POPULATION 	| NUMBER        |

**Solution**
```sql
SELECT * FROM city WHERE countrycode="JPN";
```

###Japanese Cities' Names

Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN. 

The CITY table is described as follows:

|Field 	      | Type          |
|------------ |---------------|
|ID 	        |  NUMBER       |
|NAME 	      | VARCHAR2(17)  |
|COUNTRY CODE |  	VARCHAR2(3) |
|DISTRICT 	  |  VARCHAR2(20) |
|POPULATION 	| NUMBER        |

**Solution**
```sql
SELECT name FROM city WHERE countrycode="JPN";
```

###Weather Observation Station 1

Query a list of CITY and STATE from the STATION table. 

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT city,state FROM station;
```

###Weather Observation Station 3

Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT UNIQUE city FROM station WHERE MOD(ID,2)=0 ORDER BY city ASC;
```

###Weather Observation Station 4

Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table. 

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.
For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns , because .

**SOlution**
```sql
SELECT COUNT(city) - COUNT(UNIQUE city) FROM station;
```

###Weather Observation Station 5

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically. 

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

*Sample Input*

Let's say that CITY only has four entries: DEF, ABC, PQRS and WXY

*Sample Output*

ABC 3 

PQRS 4

*Explanation*
When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths and . The longest name is PQRS, but there are options for shortest named city. Choose ABC, because it comes first alphabetically.

**solution**
```sql
SELECT city, LENGTH(city) FROM station ORDER BY LENGTH(city) DESC , city limit 1;
SELECT city, LENGTH(city) FROM station ORDER BY LENGTH(city) ASC , city limit 1;
```

###Weather Observation Station 6

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT city FROM station WHERE upper(substring(city,1,1)) IN ('a','e','i','o','u');
```

###Weather Observation Station 7

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT city FROM station WHERE lower(SUBSTRING(CITY FROM LENGTH(CITY) FOR 1)) IN ('a','e','i','o','u');
```

###Weather Observation Station 8

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT city FROM station WHERE
upper(substring(city,1,1))in ('a','e','i','o','u') AND
lower(SUBSTRING(CITY FROM LENGTH(CITY) FOR 1)) IN ('a','e','i','o','u');
```

###Weather Observation Station 9

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT city FROM station WHERE upper(substring(city,1,1)) NOT IN ('a','e','i','o','u');
```

###Weather Observation Station 10

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

The STATION table is described as follows: 

|Field  | Type        |
|-------|-------------|
|ID     | NUMBER      |
|CITY   | VARCHAR(21) |
|STATE  | VARCHAR(2)  |
|LAT_N  | NUMBER      |
|LAT_W  | NUMBER      |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT city FROM station WHERE lower(substring(city from length(city) for 1)) NOT IN ('a','e','i','o','u');
```












