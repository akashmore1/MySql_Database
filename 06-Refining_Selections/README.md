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
```
