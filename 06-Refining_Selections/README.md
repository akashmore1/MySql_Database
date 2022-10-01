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

# Challenges

1. Select all story books from books table

   ```
   SELECT title AS books FROM books WHERE title like '%stories%';
   ```

2. Find the biggest books in database

   ```
   SELECT title, pages FROM books ORDER BY pages DESC LIMIT 1;
   ```

3. Print a summary containing title and year for 3 most recent books

   ```
   SELECT CONCAT(title, ' - ', released_year) AS summary FROM books ORDER BY released_year DESC LIMIT 0, 3;
   ```

4. Find all books with authors that contains ' ' in their last name

   ```
   SELECT title, author_lname FROM books WHERE author_lname like '% %';
   ```

5. Find 3 books with lowest number in stock

   ```
    SELECT title, released_year, stock_quantity FROM books ORDER BY stock_quantity, title LIMIT 0, 3;
   ```

6. Print title and author_lname, sorted first by author_lname and then by title

   ```
    SELECT title, author_lname FROM books ORDER BY author_lname, title
   ```

7. Sorted Alphabetically By Last Name

   ```
   SELECT CONCAT('My Favourite author is ',  author_fname, ' ', author_lname, '!') as yell FROM books ORDER BY author_lname;
   ```
