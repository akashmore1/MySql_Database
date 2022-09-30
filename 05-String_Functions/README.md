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

```
SELECT REPLACE(title, 'e', '3') FROM books;
```

👆Replaces all book titles' **e** with **3**

```
SELECT
    SUBSTRING(REPLACE(title, 'e', '3'), 1, 10) AS 'weird string'
FROM books;
```

## Reverse

```
SELECT REVERSE(title) FROM books WHERE book_id = 16;
```

👆This will return reversed title of book with id 16

## CHAR_LENGTH

CHAR_LENGTH() will return length of string

```
SELECT CHAR_LENGTH('Hello world');
```

👆returns 11

## UPPER

```
SELECT UPPER('Hello World');

SELECT CONCAT('MY FAVORITE BOOK IS ', UPPER(title)) FROM books;
```

👆Returns 'HELLO WORLD'

## LOWER

```
SELECT LOWER('Hello World');

SELECT CONCAT('MY FAVORITE BOOK IS ', LOWER(title)) FROM books;
```

👆Returns 'hello world'

=====================================================================================================

# String functions exercise

1. Reverse and uppercase following Senetence:
   'Why does my cat look at me with such hatred?'

   ```
   select REVERSE(UPPER('Why does my cat look at me with such hatred?'));
   ```

2. What would be output of following code:

   ```
   SELECT
       REPLACE(
           CONCAT('I',' ','love',' ','my', ' ', 'cats'),
           ' ',
           '-'
       );
   ```

   👉 'I-love-my-cas'

3. Replace all the spaces in book title with '->'

   ```
   SELECT
       REPLACE(
           title, ' ', '->'
       ) AS title
       FROM books;
   ```

4. Print writers last name in forward and backward direction

```
SELECT
    author_lname AS forwards, REVERSE(author_lname) as backwards
    FROM books;
```
