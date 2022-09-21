# Insert Data into a table

1. Create a cats_db.
2. Create a cats table.
3. Insert some values in cats table.

code:

```
mysql-ctl cli;

CREATE DATABASE cats_db;

SHOW DATABASES;

USE cats_db;

CREATE TABLE cats(name VARCHAR(40), age INT);

SHOW TABLES;

DESC cats;
// or
SHOW COLUMNS FROM cats;

INSERT INTO cats(name, age)
VALUES ('blue', 4);

INSERT INTO cats(age, name)
VALUES (7, 'draco');
```

### How to see inserted data in a table:

Quick intro to **'SELECT'**

```
SELECT * FROM cats;
```
