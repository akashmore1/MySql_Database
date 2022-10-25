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

```
INSERT INTO photos(img_url, user_id)
VALUES('/sdcsdv', 1),
('/swdwqv', 2),
('/ewdcwd', 2);
```

# Create comments table

```
CREATE TABLE comments(
    id INT PRIMARY KEY AUTO_INCREMENT,
    comment_text VARCHAR(255) NOT NULL,
    user_id INT NOT NULL,
    photo_id INT NOT NULL,
    created_at TIMESTAMP DEFAULT now(),
    FOREIGN KEY(user_id) REFERENCES users(id),
    FOREIGN KEY(photo_id) REFERENCES photos(id)
);
```

```
INSERT INTO comments(comment_text, user_id, photo_id)
VALUES('Nice pic', 1, 2),
('Amazing pic', 3, 2),
('I <3 this!', 2, 1);
```

# Create likes table

```
CREATE TABLE likes (
    user_id INTEGER NOT NULL,
    photo_id INTEGER NOT NULL,
    created_at TIMESTAMP DEFAULT NOW(),
    FOREIGN KEY(user_id) REFERENCES users(id),
    FOREIGN KEY(photo_id) REFERENCES photos(id),
    PRIMARY KEY(user_id, photo_id)
);
```
