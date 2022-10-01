# Using Distincts

```
SELECT author_lname FROM books;

SELECT DISTINCT author_lname FROM books;

SELECT author_fname, author_lname FROM books;

SELECT DISTINCT CONCAT(author_fname,' ', author_lname) FROM books;

SELECT DISTINCT author_fname, author_lname FROM books;
```

👆 Distinct return only distinct values and eliminate repeated values

# ORDER BY

```
SELECT author_lname FROM books ORDER BY author_lname;  // Ascending author_lname

SELECT author_lname FROM books ORDER BY author_lname DESC;  // Descending author_lname

SELECT title, author_fname, author_lname  // Ascending author_fname
FROM books ORDER BY 2;

SELECT author_fname, author_lname FROM books  // Ascending author_lname and if same author_lname then ascending author_fname
ORDER BY author_lname, author_fname;
```

# LIMIT

Mostly LIMIT is used with ORDER BY

Que: Return 4 most recent books:

```
SELECT title, released_year FROM books ORDER BY released_year DESC LIMIT 4;
```

If we want to select 11th book

```
SELECT title, released_year FROM books ORDER BY released_year DESC LIMIT 10, 4;
// 0 mwans first row
// Returns 11, 12, 13, 14th row
```

If we want all data from 8th row till end of the table:

```
SELECT * FROM table LIMIT 7, 923293768728121712836182
// Second number insanely big number
```

# Searching with **LIKE**

```
SELECT author_fname FROM books WHERE author_fname LIKE '%da%';
```

👆Returns all authors first names which containes 'da' somewhere

QUE: Return all author last names starting with 'F'

```
SELECT author_lname FROM books WHERE author_lname LIKE 'f%';
```

# More Wildcard

```
SELECT title, stock_quantity FROM books WHERE stock_quantity LIKE '____';
// Returns all stock_quantity with 4 character because of 4 underscores

SELECT title, stock_quantity FROM books WHERE stock_quantity LIKE '__';
// Returns all stock_quantity with 2 character because of 2 underscores

(235)234-0987 LIKE '(___)___-____'
// returns mobile number in list of numbers

SELECT title FROM books WHERE title LIKE '%\%%'
// returns books having % in their title

SELECT title FROM books WHERE title LIKE '%\_%'
// returns books having _ in their title
```
