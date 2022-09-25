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

## Update

When you are updating something in table, make sure you are targeting correct data.
Because once updated, you can't go back.

```
UPDATE cats SET breed = 'Short hair' WHERE breed = 'Tabby';

UPDATE cats set age = 14 WHERE name = 'Misty';
```

#### Update Challenge

```
SELECT * FROM cats WHERE name='Jackson';

UPDATE cats SET name='Jack' WHERE name='Jackson';

SELECT * FROM cats WHERE name='Jackson';

SELECT * FROM cats WHERE name='Jack';

SELECT * FROM cats WHERE name='Ringo';

UPDATE cats SET breed='British Shorthair' WHERE name='Ringo';

SELECT * FROM cats WHERE name='Ringo';

SELECT * FROM cats;

SELECT * FROM cats WHERE breed='Maine Coon';

UPDATE cats SET age=12 WHERE breed='Maine Coon';

SELECT * FROM cats WHERE breed='Maine Coon';
```
