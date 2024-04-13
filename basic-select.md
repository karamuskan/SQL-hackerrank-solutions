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









