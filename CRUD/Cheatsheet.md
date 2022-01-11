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
  
   **SELECT expression FROM table_name;**

1) Read all columns from table. ```SELECT * FROM Family;```
2) Read a particular column from the table. ```SELECT name FROM Family;```
3) Read mulitple columns from the table (will be read out in the mentioned order). ```SELECT name, age, relation FROM Family;```
