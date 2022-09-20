# CODE: Creating Databases

## Creating Databases Code

Start the CLI:

**_mysql-ctl cli;_**

### List available databases:

**_show databases;_**

### The general command for creating a database:

**_CREATE DATABASE database_name;_**

A specific example:

CREATE DATABASE soap_store;

## To drop a database:

**_DROP DATABASE database_name;_**
For Example:

**_DROP DATABASE hello_world_db;_**

Remember to be careful with this command! Once you drop a database, it's gone!

## Use Database

**_USE <database name>;_**

-- example:
**_USE dog_walking_app;_**

To see which database we are using:
**_SELECT database();_**

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
)

```
