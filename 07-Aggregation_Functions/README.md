# **Agregate Functions**

These functions are used to aggregate data and find meaning in it

# Count Function

```
SELECT COUNT(*) FROM books;
```

👆 Returns all the books from books table

**QUE:** Return how many authors present in books table:

```
SELECT COUNT(DISTINCT author_fname, author_lname) as 'all authors' FROM books;
```

**QUE:** Return how many titles contain 'the' in them

```
SELECT COUNT(title) FROM books WHERE title LIKE '%the%';
```

# Group By

In group by, we group by certain records.
Supossigly in author_lname column 1 author has multiple books then we group all books written by same author
Query for above is

```
SELECT title, author_lname, COUNT(title) FROM books GROUP BY author_lname;
```

👆Output is:
![output](./output1.png)

**QUE:** Print number of books written by each author

```
SELECT
    CONCAT(author_fname, ' ', author_lname) AS Author,
    COUNT(title) AS 'No of Nooks'
    FROM books
    GROUP BY author_fname, author_lname;
```

**QUE:** Print number of books released in each year(years in ascending order)

```
SELECT
    released_year, COUNT(title)
    FROM books
    GROUP BY released_year
    ORDER BY released_year;
```

# Min and Max

Min and Max is applied on numbers
It returns Max or Min number of perticular column

**QUE:** Find latest year book is released

```
SELECT MAX(released_year) FROM books;
```
