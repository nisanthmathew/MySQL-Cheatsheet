**CHAR**

The length of a CHAR column is fixed to the length that you declare when you create the table. The length can be any value from 0 to 255. When CHAR values are stored, they are right-padded with spaces to the specified length. When CHAR values are retrieved, trailing spaces are removed unless the PAD_CHAR_TO_FULL_LENGTH SQL mode is enabled. CHAR is faster for fixed length text e.g. Sex: M/F, State Abbreviations: CA, NY, Yes/No Flags: Y/N

![Alt text](https://github.com/nisanthmathew/MySQLCheatsheet/blob/a839defcc88064abb0b7fc7b0f3523a66825b013/DataTypes/VARCHARvsCHAR.PNG?raw=true "CHAR vs VARCHAR")

**DECIMAL**

DECIMAL(M,D), where M is the total number of digits and D is the number of digits after decimal point. e.g. DECIMAL(5,2) can hold fr e.g. 999.99
M has a range of 0-65 and D has a range of 0-30

```
CREATE TABLE items(price DECIMAL(5,2));
 
INSERT INTO items(price) VALUES(7); --will be stored as 7.00 
 
INSERT INTO items(price) VALUES(7987654); --out of range or will be stored as 999.99 (max value which can be stored under specified conditions)
 
INSERT INTO items(price) VALUES(34.88); --will be stored as 34.88
 
INSERT INTO items(price) VALUES(298.9999); --will be stored as 299.00 (rounded up)

```

**FLOAT and DOUBLE**

They also stores numbers with decimal part like **DECIMAL** type. These take less space to store large numbers comapared to **DECIMAL**, but at the cost of precision.
Please always use DECIMAL where ever precision matters. or use **DOUBLE** instead of float.

![Alt text](https://github.com/nisanthmathew/MySQLCheatsheet/blob/c3618d3e8a76445dbe203eef19ec92319bb175d8/DataTypes/FLOATANDDOUBLE.PNG?raw=true "FLOAT and DOUBLE")

```
CREATE TABLE things (name VARCHAR(20), PRICE FLOAT);

INSERT INTO things (name, price) VALUES ('one', 88.45); --will be stored as 88.45

INSERT INTO things (name, price) VALUES ('two', 88333.45); --will be stored as 88333.45

INSERT INTO things (name, price) VALUES ('two', 8833334.45);  --will be stored as 8833330 (loss in precision after 7 digits)

```

**DATE, TIME and DATETIME**

```
CREATE TABLE people (name VARCHAR(100), birthdate DATE, birthtime TIME, birthdatetime DATETIME);
 
INSERT INTO people (name, birthdate, birthtime, birthdatetime)
VALUES('Padma', '1983-11-11', '10:07:35', '1983-11-11 10:07:35');
 
INSERT INTO people (name, birthdate, birthtime, birthdatetime)
VALUES('Larry', '1943-12-25', '04:10:42', '1943-12-25 04:10:42');
```

**CURDATE (gives current date), CURTIME (gives current time), and NOW (gives current datetime)

```
INSERT INTO people (name, birthdate, birthtime, birthdatetime)
VALUES('Justborn', CURDATE(), CURTIME(), NOW());
```

**FORMATTING DATE and TIME**

```
CODE: Formatting Dates
SELECT name, birthdate FROM people;
 
SELECT name, DAY(birthdate) FROM people;
 
SELECT name, birthdate, DAY(birthdate) FROM people;
 
SELECT name, birthdate, DAYNAME(birthdate) FROM people;
 
SELECT name, birthdate, DAYOFWEEK(birthdate) FROM people;
 
SELECT name, birthdate, DAYOFYEAR(birthdate) FROM people;
 
SELECT name, birthtime, DAYOFYEAR(birthtime) FROM people;
 
SELECT name, birthdt, DAYOFYEAR(birthdt) FROM people;
 
SELECT name, birthdt, MONTH(birthdt) FROM people;
 
SELECT name, birthdt, MONTHNAME(birthdt) FROM people;
 
SELECT name, birthtime, HOUR(birthtime) FROM people;
 
SELECT name, birthtime, MINUTE(birthtime) FROM people;
 
SELECT CONCAT(MONTHNAME(birthdate), ' ', DAY(birthdate), ' ', YEAR(birthdate)) FROM people;
 
SELECT DATE_FORMAT(birthdt, 'Was born on a %W') FROM people;
 
SELECT DATE_FORMAT(birthdt, '%m/%d/%Y') FROM people;
 
SELECT DATE_FORMAT(birthdt, '%m/%d/%Y at %h:%i') FROM people;
```
