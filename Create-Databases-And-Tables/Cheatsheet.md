1) Creating a database: **CREATE DATABASE database_name;** 

```CREATE DATABASE mind_palace;```

2) To drop a database: **DROP DATABASE database_name;** (Remember to be careful with this command! Once you drop a database, it's gone!)

```DROP DATABASE mind_palace;```

3) Creating a table:

**CREATE TABLE tablename
  (
    column_name data_type,
    column_name data_type
  );**
```
CREATE TABLE Family
(
  name VARCHAR(100),
  relation VARCHAR(100),
  age INT,
  picture_path VARCHAR(100)
);
```

**MySQL command line commands**

Show all databases: **SHOW DATABASES**

Use a particular database: **USE *database name***

Show tables in currently active database: **SHOW TABLES**

Show a particular column in a table: **SHOW COLUMNS FROM *table name***

