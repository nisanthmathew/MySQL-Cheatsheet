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
  
**SUBSTRING: extracts a substring from a string (starting at any position).**
    **SUBSTRING(string, start, length)**
    
  ```
   SELECT SUBSTRING ('Hello World', 2, 4);
  ```
  Output: ello
  
  ```
   SELECT SUBSTRING ('Hello World', 2);
  ```
  Output: ello World
  
  Using SUBSTRING on columns
  ```
   SELECT SUBSTRING (name, 1, 10) FROM Family;
   SELECT SUBSTRING (name, 1, 10) AS 'Short Name' FROM Family; -- Displayed column title will be 'Short Name'
   SELECT CONCAT (SUBSTRING (name, 1, 10), ...) FROM Family; -- CONCAT together with SUBSTRING
   SELECT CONCAT (SUBSTRING (name, 1, 10), ...) AS 'Short Name' FROM Family;
  ```


**REPLACE: function replaces all occurrences of a substring within a string, with a new substring.**
  Note: This function performs a case-sensitive replacement.

  **REPLACE(string, from_string, new_string)**
  
  ```
   SELECT REPLACE('Hello World', 'Hell', '%$#@');
  ```
  Output: %$#@o World

  ```
   SELECT REPLACE('Hello World', 'l', '7');
  ```
  Output: He77o Wor7d

  ```
   SELECT REPLACE('Hello World', 'o', '0');
  ```
  Output: Hell0 W0rld

  ```
   SELECT REPLACE('HellO World', 'o', '*');
  ```
  Output: HellO W*rld

 ```
   SELECT REPLACE (name, e, 3) FROM Family;
   SELECT REPLACE (name, e, 3) AS 'Weird Name' FROM Family; -- Displayed column title will be 'Weird Name'
   SELECT SUBSTRING (REPLACE (name, e, 3), 1, 10) FROM Family; -- Replace and then only display first 10 characters
   SELECT SUBSTRING (REPLACE (name, e, 3), 1, 10) AS ' Wierd Short Name' FROM Family;
  ```

**The CHAR_LENGTH() function return the length of a string (in characters).**

  **CHAR_LENGTH(string);**
  
```
  SELECT CHAR_LENGTH('Hello World');
  SELECT ame, CHAR_LENGTH(name) AS 'length' FROM FAMILY;
```

**The UPPER and LOWER() function changes the case of the string.**

  **UPPER(string);**
  **LOWER(string);**

```
 SELECT UPPER('Hello World'); -- outputs HELLO WORLD

 SELECT LOWER('Hello World'); -- outputs hello world

 SELECT UPPER(name) FROM Family;

 SELECT CONCAT('THE RELATIONSHIP IS ', UPPER(relatioship)) FROM Family;
```
