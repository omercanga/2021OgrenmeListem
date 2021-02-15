# Day-1
SQL vs MySQLSQL is the language. It outlines syntax that allows you to write queries that manage relational databases. Nothing more.

SQL is the language. It outlines syntax that allows you to write queries that manage relational databases. Nothing more.

MySQL meanwhile is a database system that runs on a server. It implements the SQL language, allowing you to write queries using its syntax to manage MySQL databases.

In addition to MySQL, there are other systems that implement SQL. Some of the more popular ones include:

PostgreSQL
SQLite
Oracle Database
Microsoft SQL Server

# Day-2
Comments
Comments allow you to explain sections of your SQL statements, or to comment out code and prevent its execution.

In SQL, there are 2 types of comments, single line and multiline.

Single Line Comments
Single line comments start with –. Any text after these 2 characters to the end of the line will be ignored.
```sql 
-- My Select query
```
SELECT * FROM users;
Multiline Comments
Multiline comments start with 
```sql 
/* and end with */
```
They stretch across multiple lines until the closing characters have been found.
```sql 

/*
This is my select query.
It grabs all rows of data from the users table
*/
SELECT * FROM users;
/*
This is another select query, which I don't want to execute yet
SELECT * FROM tasks;
*/
```

# Day-3
CHAR(size)	Fixed length string which can contain letters, numbers and special characters. The size parameter sets the maximum string length, from 0 – 255 with a default of 1.

# Day-4
VARCHAR(size)	Variable length string similar to CHAR(), but with a maximum string length range from 0 to 65535.

# Day-5
BINARY(size)	Similar to CHAR() but stores binary byte strings.

# Day-6
VARBINARY(size)	Similar to VARCHAR() but for binary byte strings.

# Day-7
TINYBLOB	Holds Binary Large Objects (BLOBs) with a max length of 255 bytes.

# Day-8
TINYTEXT	Holds a string with a maximum length of 255 characters. Use VARCHAR() instead, as it’s fetched much faster.

# Day-9
TEXT(size)	Holds a string with a maximum length of 65535 bytes. Again, better to use VARCHAR().

# Day-10
BLOB(size)	Holds Binary Large Objects (BLOBs) with a max length of 65535 bytes.

# Day-12
MEDIUMTEXT	Holds a string with a maximum length of 16,777,215 characters.

# Day-13
MEDIUMBLOB	Holds Binary Large Objects (BLOBs) with a max length of 16,777,215 bytes.

# Day-14
LONGTEXT	Holds a string with a maximum length of 4,294,967,295 characters.

# Day-11
LONGBLOB	Holds Binary Large Objects (BLOBs) with a max length of 4,294,967,295 bytes

# Day-15
BIT(size)	A bit-value type with a default of 1. The allowed number of bits in a value is set via the size parameter, which can hold values from 1 to 64.
TINYINT(size)	A very small integer with a signed range of -128 to 127, and an unsigned range of 0 to 255. Here, the size parameter specifies the maximum allowed display width, which is 255.
BOOL	Essentially a quick way of setting the column to TINYINT with a size of 1. 0 is considered false, whilst 1 is considered true.
BOOLEAN	Same as BOOL.

# Day-16
SMALLINT(size)	A small integer with a signed range of -32768 to 32767, and an unsigned range from 0 to 65535. Here, the size parameter specifies the maximum allowed display width, which is 255.
MEDIUMINT(size)	A medium integer with a signed range of -8388608 to 8388607, and an unsigned range from 0 to 16777215. Here, the size parameter specifies the maximum allowed display width, which is 255.
INT(size)	A medium integer with a signed range of -2147483648 to 2147483647, and an unsigned range from 0 to 4294967295. Here, the size parameter specifies the maximum allowed display width, which is 255.
INTEGER(size)	Same as INT.

# Day-17
BIGINT(size)	A medium integer with a signed range of -9223372036854775808 to 9223372036854775807, and an unsigned range from 0 to 18446744073709551615. Here, the size parameter specifies the maximum allowed display width, which is 255.
FLOAT(p)	A floating point number value. If the precision (p) parameter is between 0 to 24, then the data type is set to FLOAT(), whilst if its from 25 to 53, the data type is set to DOUBLE(). This behaviour is to make the storage of values more efficient.
DOUBLE(size, d)	A floating point number value where the total digits are set by the size parameter, and the number of digits after the decimal point is set by the d parameter.
DECIMAL(size, d)	An exact fixed point number where the total number of digits is set by the size parameters, and the total number of digits after the decimal point is set by the d parameter.
For size, the maximum number is 65 and the default is 10, whilst for d, the maximum number is 30 and the default is 10.
DEC(size, d)	Same as DECIMAL.
