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
