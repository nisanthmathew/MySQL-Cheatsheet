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
Please always use DECIMAL where ever precision matters.

