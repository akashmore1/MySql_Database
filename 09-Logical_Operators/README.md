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
