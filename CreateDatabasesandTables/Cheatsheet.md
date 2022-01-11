**MySQL command line commands**

Start by running the mysql service and opening the mysql shell, this can be done simultaneously with a single command:
**mysql-ctl cli**

Show all databases: **SHOW DATABASES**

Use a particular database: **USE *database name***

Show tables in currently active database: **SHOW TABLES**

Show a particular column in a table: **SHOW COLUMNS FROM *table name***

**SQL code**

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

In case you **do not want to permit null values**, you can do the following:

**CREATE TABLE tablename
  (
    column_name data_type NOT NULL,
    column_name data_type NOT NULL
  );**
```
CREATE TABLE Family
(
  name VARCHAR(100) NOT NULL,
  relation VARCHAR(100) NOT NULL,
  age INT NOT NULL,
  picture_path VARCHAR(100)
);
```

In case you wish to set **default values**, you can do the following:

**CREATE TABLE tablename
  (
    column_name data_type NOT NULL DEFAULT default_value,
    column_name data_type DEFAULT default_value
  );**
```
CREATE TABLE Family
(
  name VARCHAR(100) NOT NULL DEFAULT 'NA',
  relation VARCHAR(100) NOT NULL DEFAULT 'NA',
  age INT NOT NULL DEFAULT 0,
  picture_path VARCHAR(100) DEFAULT 'NA'
);
```

Inoder to create a table with **primary key constraints**, you can do the following:

**CREATE TABLE tablename
  (
    column_name1 data_type1 NOT NULL,
    column_name2 data_type2,
    PRIMARY KEY (column_name1)
  );**
  
```
CREATE TABLE Family
(
  person_id INT NOT NULL,
  name VARCHAR(100) NOT NULL DEFAULT 'NA',
  relation VARCHAR(100) NOT NULL DEFAULT 'NA',
  age INT NOT NULL DEFAULT 0,
  picture_path VARCHAR(100) DEFAULT 'NA',
  PRIMARY KEY (person_id)
);
```

Adding **auto increment** to primary key

```
CREATE TABLE Family
(
  person_id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(100) NOT NULL DEFAULT 'NA',
  relation VARCHAR(100) NOT NULL DEFAULT 'NA',
  age INT NOT NULL DEFAULT 0,
  picture_path VARCHAR(100) DEFAULT 'NA',
  PRIMARY KEY (person_id)
);
```

please note: A primary key is a column or a set of columns in a table whose values uniquely identify a row in the table. A relational database is designed to enforce the uniqueness of primary keys by allowing only one row with a given primary key value in a table.


4) Dropping or deleting a table

**DROP TABLE tablename**

```DROP TABLE Family```
