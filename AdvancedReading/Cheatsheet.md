1) **SELECT DISTINCT statement is used to return only distinct (different) values.**

   SELECT DISTINCT column1, column2, .. FROM table_name;
    
    
    SELECT DISTINCT name FROM Family;
    SELECT DISTINCT name, relationship FROM Family; -- returns distinct of the combination of name and relationship
    
 2) **The ORDER BY keyword is used to sort the result-set in ascending or descending order.**

   The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the **DESC** keyword.

   SELECT column1, column2, ...
   FROM table_name
   ORDER BY column1, column2, ... ASC|DESC;
   
   ```
   SELECT name FROM Family ORDER BY age DESC;
   SELECT name, relationship, age FROM Family ORDER BY 3; --this will sorting using age since age is in the 3rd position.
   SELECT first_name, last_name FROM Family ORDER BY last_name, first_name; --this will sort first using last name and then using first name in case last names match.
   ```

3) **LIMIT statement limits the output by the specified number**

   SELECT column1, column2.. FROM table_name LIMIT limit_number;
   
   ```
   SELECT name FROM Family LIMIT 2; -- displays only two entries
   SELECT name FROM Family ORDER BY age LIMIT 2; -- displays only two youngest entries
   SELECT name FROM Family ORDER BY age LIMIT 1,3; -- displays only two young entries except the youngest entry
   ```
4) **LIKE operator is used in a WHERE clause to search for a specified pattern in a column.**

   There are two wildcards often used in conjunction with the LIKE operator:
      The percent sign (%) represents zero, one, or multiple characters.
      The underscore sign (_) represents one, single character
      
   SELECT column1, column2, ...
   FROM table_name
   WHERE columnN LIKE pattern;
   
   ```
   SELECT name FROM Family WHERE name LIKE 'a%';	--Finds any values that start with "a"
   SELECT name FROM Family WHERE name LIKE '%a';	--Finds any values that end with "a"
   SELECT name FROM Family WHERE name LIKE '%or%';	--Finds any values that have "or" in any position
   SELECT name FROM Family WHERE name LIKE '_r%';	--Finds any values that have "r" in the second position
   SELECT name FROM Family WHERE name LIKE 'a_%';	--Finds any values that start with "a" and are at least 2 characters in length
   SELECT name FROM Family WHERE name LIKE 'a__%';	--Finds any values that start with "a" and are at least 3 characters in length
   SELECT name FROM Family WHERE name LIKE 'a%o';	--Finds any values that start with "a" and ends with "o"
```
