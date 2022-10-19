# Not equal (!=)

```
SELECT title FROM books WHERE released_year = 2017;

SELECT title FROM books WHERE released_year != 2017;

SELECT title, author_lname FROM books;

SELECT title, author_lname FROM books WHERE author_lname = 'Harris';

SELECT title, author_lname FROM books WHERE author_lname != 'Harris';
```

# Not Like

Select all books that start with 'W'

```
SELECT title FROM books WHERE title LIKE 'W%';
```

Select all books that ❌don't start with 'W'

```
SELECT title FROM books WHERE title NOT LIKE 'W%';
```

# Greater than (>)

Select all books released after year 2000

```
SELECT * FROM books WHERE released_year > 2000;
```

Greater than or equal to

```
SELECT * FROM books WHERE released_year >= 2000;
```

Select all books for selling where stock quantity is more than 100.

```
SELECT title, stock_quantity FROM books WHERE stock_quantity >=100;
```

Colt's code (Some imp things👇)

```
SELECT title, released_year FROM books ORDER BY released_year;

SELECT title, released_year FROM books
WHERE released_year > 2000 ORDER BY released_year;

SELECT title, released_year FROM books
WHERE released_year >= 2000 ORDER BY released_year;

SELECT title, stock_quantity FROM books;

SELECT title, stock_quantity FROM books WHERE stock_quantity >= 100;

SELECT 99 > 1;

SELECT 99 > 567;

100 > 5
-- true

-15 > 15
-- false

9 > -10
-- true

1 > 1
-- false

'a' > 'b'
-- false

'A' > 'a'
-- false

'A' >=  'a'
-- true

SELECT title, author_lname FROM books WHERE author_lname = 'Eggers';

SELECT title, author_lname FROM books WHERE author_lname = 'eggers';

SELECT title, author_lname FROM books WHERE author_lname = 'eGGers';
```

# Less than (<)

```
SELECT title, released_year FROM books;

SELECT title, released_year FROM books
WHERE released_year < 2000;

SELECT title, released_year FROM books
WHERE released_year <= 2000;

SELECT 3 < -10;
-- false

SELECT -10 < -9;
-- true

SELECT 42 <= 42;
-- true

SELECT 'h' < 'p';
-- true

SELECT 'Q' <= 'q';
-- true
```

# Logical AND (&&)

1. All conditions must be true
2. We can use both 'AND' and '&&' operators in MySql

```
SELECT title, author_lname, released_year FROM books
WHERE author_lname='Eggers';

SELECT title, author_lname, released_year FROM books
WHERE released_year > 2010;

SELECT
    title,
    author_lname,
    released_year FROM books
WHERE author_lname='Eggers'
    AND released_year > 2010;

SELECT 1 < 5 && 7 = 9;
-- false

SELECT -10 > -20 && 0 <= 0;
-- true

SELECT -40 <= 0 AND 10 > 40;
--false

SELECT 54 <= 54 && 'a' = 'A';
-- true

SELECT *
FROM books
WHERE author_lname='Eggers'
    AND released_year > 2010
    AND title LIKE '%novel%';
```

Please note, as of MySQL 8.0.17, the && operator is deprecated and support for it will be removed in a future MySQL version.
Applications should be adjusted to use the standard SQL AND operator.
If you're using MySQL 5.7 or older, which most of you are if you're using GoormIDE, then you don't have to worry about this right now.
But, in newer versions of MySQL (8.0.17 and newer) you will need to replace && with AND.

# Logical OR (||)

One of the condition is true

```
SELECT
    title,
    author_lname,
    released_year
FROM books
WHERE author_lname='Eggers' || released_year > 2010;


SELECT 40 <= 100 || -2 > 0;
-- true

SELECT 10 > 5 || 5 = 5;
-- true

SELECT 'a' = 5 || 3000 > 2000;
-- true

SELECT title,
       author_lname,
       released_year,
       stock_quantity
FROM   books
WHERE  author_lname = 'Eggers'
              || released_year > 2010
OR     stock_quantity > 100;
```

Please note, as of MySQL 8.0.17, the || operator is deprecated and support for it will be removed in a future MySQL version.
Applications should be adjusted to use the standard SQL OR operator.
If you're using MySQL 5.7 or older, which most of you are if you're using GoormIDE, then you don't have to worry about this right now.
But, in newer versions of MySQL (8.0.17 and newer) you will need to replace || with OR.

# Between

Find all books released in between 2000 to 2014

```
SELECT * FROM books WHERE released_year >= 2000 AND released_year <= 2014;
```

👆We can do like this with logic.
However there is BETWEEN .. AND .. operator

```
SELECT * FROM books WHERE released_year BETWEEN 2000 AND 2014;
```

**NOT BETWEEN** is also a thing

## CAST('something' AS DATETIME)

While using BETWEEN for dates and times, it is highly recommented that to convert these into **DATETIME** and then apply BETWEEN

```
SELECT CAST('2017-05-02' AS DATETIME);

use new_testing_db;

SELECT name, birthdt FROM people WHERE birthdt BETWEEN '1980-01-01' AND '2000-01-01';

SELECT
    name,
    birthdt
FROM people
WHERE
    birthdt BETWEEN CAST('1980-01-01' AS DATETIME)
    AND CAST('2000-01-01' AS DATETIME);
```

# IN

Select all books written by...
Carver, Lahiri, Smith

```
SELECT title, author_lname FROM books
WHERE author_lname='Carver' OR
      author_lname='Lahiri' OR
      author_lname='Smith';
```

**IN** makes it much easier

```
SELECT title, author_lname FROM books
WHERE author_lname IN ('Carver', 'Lahiri', 'Smith');
```

Select all books not published in
2000,
2002,
2004,
2006,
2008,
2010,
2012,
2014,
2016

either👇

```
SELECT title, released_year FROM books
WHERE released_year != 2000 AND
      released_year != 2002 AND
      released_year != 2004 AND
      released_year != 2006 AND
      released_year != 2008 AND
      released_year != 2010 AND
      released_year != 2012 AND
      released_year != 2014 AND
      released_year != 2016;
```

or👇

```
SELECT title, released_year FROM books
WHERE released_year NOT IN
(2000,2002,2004,2006,2008,2010,2012,2014,2016);
```

or👇 better way

```
SELECT title, released_year FROM books
WHERE released_year >= 2000 AND
released_year % 2 != 0;
```

# Case Statements

Print title, released_year, genre("new column, if(year >=200) then 'Modern' or 'Old'")

```
SELECT title, released_year, CASE WHEN released_year >= 2000 THEN 'Modern' ELSE 'OLD' END FROM books;
```

```
SELECT title, released_year,
       CASE
         WHEN released_year >= 2000 THEN 'Modern Lit'
         ELSE '20th Century Lit'
       END AS GENRE
FROM books;
```
