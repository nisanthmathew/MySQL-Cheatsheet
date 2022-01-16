**COUNT() function returns the number of rows that matches a specified criterion.**

  SELECT COUNT(column_name) FROM table_name;

  ```
  SELECT COUNT(relationship) FROM Family; --counts number of relationships
  SELECT COUNT(DISTINCT relationship) FROM Family; --counts number of unique relationships
  SELECT COUNT(*) FROM Family WHERE relationship LIKE '%Friend%'; --counts number of friends in relationships
  ```
