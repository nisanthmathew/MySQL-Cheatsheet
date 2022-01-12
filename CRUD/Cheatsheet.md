This Cheatsheet provides info about CRUD - Create Read Update and Delete

**CREATE (in other words add or insert data into tables)**
1) Insert data into table:

    **INSERT INTO table_name(column_name) VALUES (data);**

    ```INSERT INTO Family(name, relation, age, picture_path) VALUES ('Mom', 'Mother', 50, '/usr/mindpalace/Family/Mom.jpg);```
    

2) Insert multiple rows of data into table:

     **INSERT INTO table_name(column_name) VALUES (data1, data2, data3, ...);**
     
     ```
     INSERT INTO Family(name, relation, age, picture_path) VALUES ('Mom', 'Mother', 50, '/usr/mindpalace/Family/Mom.jpg), 
        ('Dad', 'Father', 54, '/usr/mindpalace/Family/Dad.jpg), 
        ('Bro', 'Brother', 25, '/usr/mindpalace/Family/Bro.jpg);


**READ (retrieve and search data)**
  
1) **SELECT expression FROM table_name;**

      a) Read all columns from table. ```SELECT * FROM Family;```

      b) Read a particular column from the table. ```SELECT name FROM Family;```

      c) Read mulitple columns from the table (will be read out in the mentioned order). ```SELECT name, age, relation FROM Family;```
   
2) The **WHERE** clause is used to filter records. It is used to extract only those records that fulfill a specified condition.
   
   **SELECT expression FROM table_name WHERE conditional_expression;**
   
   ```SELECT name FROM Family WHERE age < 30;```

3) **ALIASES** modifies the displayed column names
   
   ```
   SELECT name AS Person, age, relation FROM Family;
 
   SELECT name AS 'Person Name', age, relation FROM Family;
   ```
   
**UPDATE (alter existing data)**

   **UPDATE table_name SET thing_or_things_to_be_changed WHERE condition;**
   
   ```
   UPDATE Family SET age=55, name='Daddy' WHERE relation='Father' ;
   ```
