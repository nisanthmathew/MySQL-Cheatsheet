This Cheatsheet provides info about functions for string manipulation.

**CONCAT: adds two or more expressions together.**

  **CONCAT(expression1, expression2, expression3,...)**
  Note: If any of the expressions is a NULL value, it returns NULL. Also note that the data in the database remains unmodified.
  
   ```
   SELECT CONCAT (name, 'is your', relation) FROM Family;
   SELECT CONCAT (name, 'is your', relation) AS 'Relationships' FROM Family;
  ```
**CONCAT_WS: adds two or more expressions together when we need them to be seperated using a separator.**

  **CONCAT_WS(separator, expression1, expression2, expression3,...)**
  
   ```
   SELECT CONCAT_WS(' | ', name, age, relation) FROM Family;
  ```
