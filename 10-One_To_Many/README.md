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
