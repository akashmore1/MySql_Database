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

## Substring

**SUBSTRING()** function is more like **slice()** in javascrpt

```
SELECT SUBSTRING('Hello World', 1, 4);
```

should return **Hell**

```
SELECT SUBSTRING('Hello World', 3);
```

should return **llo World**

```
SELECT SUBSTRING(title, 1, 10) FROM books;
```

should return title of book with only first 10 characters.

```
SELECT CONCAT
    (
        SUBSTRING(title, 1, 10),
        '...'
    )
FROM books;
```

should return title of book with only first 10 characters, with '...' ahead indicating there is more string ahead
In this way we can use caoncat and substring together in select

## Replace

1. REPLACE() method replaces every occurance.
2. REPLACE() method is case sentitive.

```
SELECT REPLACE('one two three four', ' ', ' and ');
```

should return **one and two and three and four**
