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
