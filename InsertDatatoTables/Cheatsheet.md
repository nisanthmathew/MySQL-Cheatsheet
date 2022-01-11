1) Insert data into table:

    **INSERT INTO table_name(column_name) VALUES (data);**

    ```INSERT INTO Family(name, relation, age, picture_path) VALUES ('Mom', 'Mother', 50, '/usr/mindpalace/Family/Mom.jpg);```
    

2) Insert multiple rows of data into table:

     **INSERT INTO table_name(column_name) VALUES (data1, data2, data3, ...);**
     
     ```
     INSERT INTO Family(name, relation, age, picture_path) VALUES ('Mom', 'Mother', 50, '/usr/mindpalace/Family/Mom.jpg), 
        ('Dad', 'Father', 54, '/usr/mindpalace/Family/Dad.jpg), 
        ('Bro', 'Brother', 25, '/usr/mindpalace/Family/Bro.jpg);
     ```


3) To view all the rows in a table:

    **SELECT * FROM table_name;**

    ```SELECT * FROM Family;```
