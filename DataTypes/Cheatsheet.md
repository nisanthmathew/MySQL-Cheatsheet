**CHAR**

The length of a CHAR column is fixed to the length that you declare when you create the table. The length can be any value from 0 to 255. When CHAR values are stored, they are right-padded with spaces to the specified length. When CHAR values are retrieved, trailing spaces are removed unless the PAD_CHAR_TO_FULL_LENGTH SQL mode is enabled. CHAR is faster for fixed length text e.g. Sex: M/F, State Abbreviations: CA, NY, Yes/No Flags: Y/N

![Alt text](https://github.com/nisanthmathew/MySQLCheatsheet/blob/a839defcc88064abb0b7fc7b0f3523a66825b013/DataTypes/VARCHARvsCHAR.PNG?raw=true "CHAR vs VARCHAR")
