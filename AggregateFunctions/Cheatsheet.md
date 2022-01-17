**COUNT() function returns the number of rows that matches a specified criterion.**

  SELECT COUNT(column_name) FROM table_name;

  ```
  SELECT COUNT(relationship) FROM Family; --counts number of relationships
  SELECT COUNT(DISTINCT relationship) FROM Family; --counts number of unique relationships
  SELECT COUNT(*) FROM Family WHERE relationship LIKE '%Friend%'; --counts number of friends in relationships
  ```


**GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".**

  The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

  SELECT column_name(s) FROM table_name WHERE condition GROUP BY column_name(s);
  
  ```
  SELECT relationships COUNT(*) FROM Family GROUP BY relationship; --groups similar relationships and prints their counts
  ```

**The MIN() function returns the smallest value of the selected column.**

  MIN() Syntax SELECT MIN(column_name) FROM table_name WHERE condition;
  
  ```
  SELECT MIN(age) FROM Family; --returns minimum age
  SELECT relationship, MIN(age) FROM Family GROUP BY relationship; --returns minimum age in each relationship category
  ```

**The MAX() function returns the largest value of the selected column.**

  MAX() Syntax SELECT MIN(column_name) FROM table_name WHERE condition;
  
  ```
  SELECT MAX(age) FROM Family; --returns maximum age
  ```
  
  **Please Note**: if you un the following query ```SELECT name, MAX(age) FROM Family;``` this will not return the name of the oldest person. Instead it will simply return the   first name. On potential way to make it work is to use **SUBQUERIES** eventhough it is a bit inefficient (due to two queries). Here is how to do it:
 
  ```
  SELECT name, relationship FROM Family WHERE age = (SELECT MAX(age) FROM Family); --returns name and relaionship of oldest person with age
  ```

**AVG() function returns the average value of a numeric column.**

  SELECT AVG(column_name) FROM table_name WHERE condition;
  
  ```
  SELECT AVG(age) FROM Family; --returns average age from family
  SELECT relationship, AVG(age) FROM Family GROUP BY relationship; --returns average age grouped by relationship
  ```

**SUM() function returns the total sum of a numeric column.**

  SELECT SUM(column_name) FROM table_name WHERE condition;
  
  ```
  SELECT SUM(age) FROM Family; --returns sum of all ages from family
  SELECT relationship, SUM(age) FROM Family GROUP BY relationship; --returns sum of all ages grouped by relationship
  ```
