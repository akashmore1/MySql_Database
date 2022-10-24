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

# Create photos table

```
CREATE TABLE photos(
    id INT PRIMARY KEY AUTO_INCREMENT,
    img_url VARCHAR(255) NOT NULL,
    user_id INT NOT NULL,
    created_at TIMESTAMP DEFAULT now(),
    FOREIGN KEY(user_id) REFERENCES users(id)
);
```
