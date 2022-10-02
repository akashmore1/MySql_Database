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
