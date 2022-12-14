## Real world data can be messy

# Relationships basics

1. One to one relationship
2. One to many relationship
3. Many to many relationship

# Maintaining data in two tables

![Two tables](./pimary-foreign_key.png)

# Foreign key

In below example customer_id is a foreign key

```
CREATE TABLE customers(
    id INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
    first_name VARCHAR(40),
    last_name VARCHAR(40),
    email VARCHAR(40)
);

CREATE TABLE orders(
    id INT AUTO_INCREMENT PRIMARY KEY NOT NULL,
    order_date DATETIME,
    amount DECIMAL(8, 2),
    customer_id INT,
    FOREIGN KEY(customer_id) REFERENCES customers(id)
);
```

# Cross Join

## Finding Orders Placed By George: 2 Step Process

```
SELECT id FROM customers WHERE last_name='George';
SELECT * FROM orders WHERE customer_id = 1;
```

## Finding Orders Placed By George: Using a subquery

```
SELECT * FROM orders WHERE customer_id =
(
SELECT id FROM customers
WHERE last_name='George'
);
```

## Cross Join Craziness

In cross join, every record of first table is mapped to every record of second table.

```
SELECT * FROM customers, orders;
```

# Inner Join

## IMPLICIT INNER JOIN

```
SELECT * FROM customers, orders
WHERE customers.id = orders.customer_id;
```

## IMPLICIT INNER JOIN

SELECT first_name, last_name, order_date, amount
FROM customers, orders
WHERE customers.id = orders.customer_id;

## EXPLICIT INNER JOINS

```
SELECT * FROM customers
JOIN orders
ON customers.id = orders.customer_id;
```

```
SELECT first_name, last_name, order_date, amount
FROM customers
JOIN orders
ON customers.id = orders.customer_id;
```

```
SELECT *
FROM orders
JOIN customers
ON customers.id = orders.customer_id;
```

## ARBITRARY JOIN - meaningless, but still possible

```
SELECT * FROM customers
JOIN orders ON customers.id = orders.id;
```

# LEFT JOIN

```
SELECT first_name, last_Name, order_date, amount
FROM customers
LEFT JOIN orders
  ON customers.id = orders.customer_id;
```

This will return

![left join](./leftjoin.png)

We can have default value for null, with **IFNULL**

```
SELECT
    first_name,
    last_name,
    IFNULL(SUM(amount), 0) AS total_spent
FROM customers
LEFT JOIN orders
    ON customers.id = orders.customer_id
GROUP BY customers.id
ORDER BY total_spent;
```

# RIGHT JOIN

1. Right Join is similar to left join
2. If we apply left join on cutstomer(reverse order of joining) and apply right join, it is exactly like left join in baove example

```
SELECT * FROM customers
RIGHT JOIN orders
    ON customers.id = orders.customer_id;
```

```
SELECT
    IFNULL(first_name,'MISSING') AS first,
    IFNULL(last_name,'USER') as last,
    order_date,
    amount,
    SUM(amount)
FROM customers
RIGHT JOIN orders
    ON customers.id = orders.customer_id
GROUP BY first_name, last_name;
```

# Working with deleting cascade

When we want to delete something from customers table, it gives error because customer id is foreign key in orders table.
In order to allow user to delete user from customers table and all his orders from orders table, we use **DELETE CASCADE**

```
CREATE TABLE customers(
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    email VARCHAR(100)
);

CREATE TABLE orders(
    id INT AUTO_INCREMENT PRIMARY KEY,
    order_date DATE,
    amount DECIMAL(8,2),
    customer_id INT,
    FOREIGN KEY(customer_id)
        REFERENCES customers(id)
        ON DELETE CASCADE
);
```

# One to many exercise

Que: Create students and paper table

```
CREATE TABLE students(
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(40)
);

CREATE TABLE papers(
    title VARCHAR(40),
    grade DECIMAL(4, 1),
    student_id INT,
    FOREIGN KEY(student_id) REFERENCES students(student_id)
)

INSERT INTO students (first_name) VALUES
('Caleb'), ('Samantha'), ('Raj'), ('Carlos'), ('Lisa');

INSERT INTO papers (student_id, title, grade ) VALUES
(1, 'My First Book Report', 60),
(1, 'My Second Book Report', 75),
(2, 'Russian Lit Through The Ages', 94),
(2, 'De Montaigne and The Art of The Essay', 98),
(4, 'Borges and Magical Realism', 89);
```

QUE: PRINT student, title, grade with desc grade

```
SELECT first_name, title, grade
FROM students
INNER JOIN papers
ON  students.student_id = papers.student_id
ORDER BY grade DESC;
```

QUE: Print all students and then their paper title with grade

```
SELECT first_name, title, grade
FROM students
LEFT JOIN papers ON students.student_id = papers.student_id;
```

QUE: Print average grades of all students, with desc order

```
SELECT first_name, AVG(IFNULL(grade, 0)) AS average
FROM students
LEFT JOIN papers
ON students.student_id = papers.student_id
GROUP BY first_name
ORDER BY average DESC;
```

QUE: Print name, avearge grade, passing status.
(If avg > 75% then pass or fail)

```
SELECT first_name, AVG(IFNULL(grade, 0)) AS average,
CASE
    WHEN AVG(IFNULL(grade, 0)) >= 75 THEN 'PASS'
    ELSE 'FAIL'
END AS passing_status
FROM students
LEFT JOIN papers
ON students.student_id = papers.student_id
GROUP BY first_name
ORDER BY average DESC;
```
