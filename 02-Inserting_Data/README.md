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

### Inserting multiple values in DB:

```
INSERT INTO cats(name, age)
VALUES ('blue', 21),
        ('philip', 10),
        ('gray', 4);
```

# Insert Challenge

Create a people database with first_name, last_name, age columns

```
CREATE TABLE people(first_name VARCHAR(20), last_name VARCHAR(20), age INT);

SHOW TABLES;

DESC people;
// or
SHOW COLUMNS FROM people;

INSERT INTO people(first_name, last_name, age)
VALUES('Akash', 'More', 23);

INSERT INTO people(age, first_name, last_name)
VALUES(13, 'Tina', 'Belcher'),
      (42, 'Bob', 'Belcher');

INSERT INTO people(first_name, last_name, age)
VALUES('Linda', 'Belcher', 45),
VALUES('Philip', 'Frond', 38),
VALUES('Calvin', 'Fischoder', 70);
```
