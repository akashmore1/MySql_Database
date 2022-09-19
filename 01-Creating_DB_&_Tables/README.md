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

### To drop a database:

**_DROP DATABASE database_name;_**
For Example:

**_DROP DATABASE hello_world_db;_**

Remember to be careful with this command! Once you drop a database, it's gone!

### Use Database

**_USE <database name>;_**

-- example:
**_USE dog_walking_app;_**

To see which database we are using:
**_SELECT database();_**
