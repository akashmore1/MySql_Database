# Create instagram datbase

```
CREATE DATABASE ig_clone;
USE ig_clone;
```

# Create user table

```
CREATE table users(
    id INT PRIMARY KEY AUTO_INCREMENT,
    user_name VARCHAR(255) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT now()
);
```

# Insert data into users

```
INSERT INTO users(user_name)
VALUES('BlueTheCat'),
('CharlieBrown'),
('ColtSteele');
```
