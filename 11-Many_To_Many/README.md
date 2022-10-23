# Many to many

Some examples
![Some examples](./Examples_manytomany.png)

Imagine we're building a tv show reviewing application.
We can have table schema like below

![table schema](./manytomany-tables.png)

# Create tables

1. Reviewer table

```
CREATE TABLE reviewers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100),
    last_name VARCHAR(100)
);
```
