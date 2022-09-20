# CODE: Creating Databases

## Creating Databases Code

Start the CLI:

**_mysql-ctl cli;_**

### List available databases:

```
show databases;
```

### The general command for creating a database:

```
CREATE DATABASE database_name;
```

A specific example:

CREATE DATABASE soap_store;

## To drop a database:

**_DROP DATABASE database_name;_**
For Example:

```
DROP DATABASE hello_world_db;
```

Remember to be careful with this command! Once you drop a database, it's gone!

## Use Database

**_USE <database name>;_**

-- example:

```
USE dog_walking_app;
```

To see which database we are using:

```
SELECT database();
```

## Tables!

1. The True Heart of SQL
2. A database is just a bunch of tables
3. In a relational database, at least
4. Tables Hold The Data! ("a collection of related data held in a structured format within a database")

# Datatypes

1. **_int_** : INT is by default signed, INT (which is shorthand for INT SIGNED) therefore has the MAX VALUE of 2147483647. INT UNSIGNED is 0 to 4294967295.
2. **_varchar_**: ranges from 0 to 255 chars

![Datatype challenge](./Datatype_Challenge_Sol.png)

# Creating Tables

```
CREATE TABLE tablename
(
    column_name datatype,
    column_name datatype
);
```

### Example for cats table:

```
CREATE TABLE cats
(
    name VARCHAR(100),
    age INT
);
```

### How to know tables are created?

```
SHOW tables;
```

### To know all columns in given table:

```
SHOW COLUMNS FROM <table_name>;
```

or

```
DESC <table_name>;
```
