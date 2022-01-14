**SELECT DISTINCT statement is used to return only distinct (different) values.**

   SELECT DISTINCT column1, column2, .. FROM table_name;
    
    
    SELECT DISTINCT name FROM Family;
    SELECT DISTINCT name, relationship FROM Family; -- returns distinct of the combination of name and relationship
    
 **The ORDER BY keyword is used to sort the result-set in ascending or descending order.**

   The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the **DESC** keyword.

   SELECT column1, column2, ...
   FROM table_name
   ORDER BY column1, column2, ... ASC|DESC;
   
   ```
   SELECT name FROM Family ORDER BY age DESC;
   SELECT name, relationship, age FROM Family ORDER BY 3; --this will sorting using age since age is in the 3rd position.
   SELECT first_name, last_name FROM Family ORDER BY last_name, first_name; --this will sort first using last name and then using first name in case last names match.
   ```

**LIMIT statement limits the output by the specified number**

   SELECT column1, column2.. FROM table_name LIMIT limit_number;
   
   ```
   SELECT name FROM Family LIMIT 2; -- displays only two entries
   SELECT name FROM Family ORDER BY age LIMIT 2; -- displays only two youngest entries
   SELECT name FROM Family ORDER BY age LIMIT 1,3; -- displays only two young entries except the youngest entry
   ```
