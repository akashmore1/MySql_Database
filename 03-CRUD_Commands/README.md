# CRUD Commands

## Create:

```
INSERT INTO cats(name, age) VALUES(‘Taco’, 14);
```

## Read:

### SELECT:

```
SELECT * FROM CATS;
```

👆 This means show add columns from cats database(name, id, age, breed)

#### If we only want name of all cats:

```
SELECT name FROM cats;
```

#### If we want multiple columns (but not all) from cats:

```
SELECT name, age FROM cats;
```

### WHERE:

If we want specific data in a table.

```
SELECT * FROM cats WHERE age = 4;
```

### Aliases

When aliases are used?
When we join two tables, if both of them have some columns named same, we use aliases.

```
SELECT cat_id AS id, name FROM cats;

SELECT name AS 'cat name', breed AS 'kitty breed' FROM cats;

DESC cats;
```
