# String Functions

## Concat

```
SELECT
  CONCAT(author_fname, ' ', author_lname) AS full_name
FROM books;
```

shoud return **Akash More**

### ConcatWs (concat with symbol)

```
SELECT
    CONCAT_WS(' - ', title, author_fname, author_lname)
FROM books;
```

should return **Mrityunjay - Shivaji - Samant**
