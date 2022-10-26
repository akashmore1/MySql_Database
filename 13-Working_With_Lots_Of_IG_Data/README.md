# Challenges

1. Que: Find 4 oldest users.

```
SELECT * FROM users
ORDER BY created_at
LIMIT 4;
```

2. Que: What day of week most users registered on

```
SELECT DAYNAME(users.created_at) as day_name
FROM users
GROUP BY day_name
ORDER BY COUNT(day_name) DESC
LIMIT 1;
```

3. Que: Find inactive users. Never posted a photo.

```
SELECT users.username, photos.id
FROM users
LEFT JOIN photos
    ON users.id = photos.user_id
WHERE photos.id IS NULL;
```

4. Que: Find most liked instagram photo and its user

```
SELECT users.username, photos.user_id, likes.photo_id,
COUNT(likes.photo_id)
FROM likes
JOIN photos
    on photos.id = likes.photo_id
JOIN users
    ON photos.user_id = users.id
GROUP BY likes.photo_id
ORDER BY COUNT(likes.photo_id) DESC
LIMIT 4;
```

5. Que: Find average numbers of photos every users has

```
SELECT(
    (SELECT COUNT(photos.id) FROM photos) /
    (SELECT COUNT(users.id) FROM users)
);
```

6. Que: Top 4 most used hashtags

```
SELECT
	tags.tag_name,
    COUNT(photo_tags.photo_id),
    photo_tags.tag_id
FROM tags
JOIN photo_tags
    ON tags.id = photo_tags.tag_id
GROUP BY photo_tags.tag_id
ORDER BY COUNT(photo_tags.photo_id) DESC
LIMIT 4;
```
